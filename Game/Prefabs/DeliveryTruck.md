# Game.Prefabs.DeliveryTruck

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DeliveryTruck : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_CargoCapacity;
    public System.Int32 m_CostToDrive;
    public Game.Economy.ResourceInEditor[] m_TransportedResources;

    public DeliveryTruck();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_CargoCapacity`  

```csharp
public System.Int32 m_CargoCapacity;
```

- `public System.Int32 m_CostToDrive`  

```csharp
public System.Int32 m_CostToDrive;
```

- `public Game.Economy.ResourceInEditor[] m_TransportedResources`  

```csharp
public Game.Economy.ResourceInEditor[] m_TransportedResources;
```


## Constructors

- `public DeliveryTruck()`  

```csharp
public DeliveryTruck();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Vehicles.DeliveryTruck>());
		if (base.prefab is CarPrefab)
		{
			components.Add(ComponentType.ReadWrite<PathInformation>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<DeliveryTruckData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		DeliveryTruckData componentData = new DeliveryTruckData
		{
			m_CargoCapacity = m_CargoCapacity,
			m_CostToDrive = m_CostToDrive
		};
		if (m_TransportedResources != null)
		{
			for (int i = 0; i < m_TransportedResources.Length; i++)
			{
				componentData.m_TransportedResources |= EconomyUtils.GetResource(m_TransportedResources[i]);
			}
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


