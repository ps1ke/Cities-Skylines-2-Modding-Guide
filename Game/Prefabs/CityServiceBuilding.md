# Game.Prefabs.CityServiceBuilding

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CityServiceBuilding : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public Game.Prefabs.ServiceUpkeepItem[] m_Upkeeps;

    public CityServiceBuilding();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ServiceUpkeepItem[] m_Upkeeps`  

```csharp
public Game.Prefabs.ServiceUpkeepItem[] m_Upkeeps;
```


## Constructors

- `public CityServiceBuilding()`  

```csharp
public CityServiceBuilding();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (GetComponent<ServiceUpgrade>() == null)
		{
			components.Add(ComponentType.ReadWrite<CityServiceUpkeep>());
			components.Add(ComponentType.ReadWrite<Resources>());
			components.Add(ComponentType.ReadWrite<TripNeeded>());
			components.Add(ComponentType.ReadWrite<GuestVehicle>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		if ((m_Upkeeps != null && m_Upkeeps.Length != 0) || (base.prefab.TryGet<ServiceConsumption>(out var component) && component.m_Upkeep > 0))
		{
			components.Add(ComponentType.ReadWrite<ServiceUpkeepData>());
		}
		components.Add(ComponentType.ReadWrite<CollectedServiceBuildingBudgetData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<CityServiceUpkeep>());
		components.Add(ComponentType.ReadWrite<Resources>());
		components.Add(ComponentType.ReadWrite<TripNeeded>());
		components.Add(ComponentType.ReadWrite<GuestVehicle>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		DynamicBuffer<ServiceUpkeepData> dynamicBuffer = entityManager.AddBuffer<ServiceUpkeepData>(entity);
		if (m_Upkeeps != null)
		{
			ServiceUpkeepItem[] upkeeps = m_Upkeeps;
			foreach (ServiceUpkeepItem serviceUpkeepItem in upkeeps)
			{
				dynamicBuffer.Add(new ServiceUpkeepData
				{
					m_Upkeep = new ResourceStack
					{
						m_Resource = EconomyUtils.GetResource(serviceUpkeepItem.m_Resources.m_Resource),
						m_Amount = serviceUpkeepItem.m_Resources.m_Amount
					},
					m_ScaleWithUsage = serviceUpkeepItem.m_ScaleWithUsage
				});
			}
		}
	}
```


