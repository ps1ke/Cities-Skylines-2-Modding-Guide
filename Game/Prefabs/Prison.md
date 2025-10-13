# Game.Prefabs.Prison

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Prison : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_PrisonVanCapacity;
    public System.Int32 m_PrisonerCapacity;
    public System.SByte m_PrisonerWellbeing;
    public System.SByte m_PrisonerHealth;

    public Prison();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_PrisonVanCapacity`  

```csharp
public System.Int32 m_PrisonVanCapacity;
```

- `public System.Int32 m_PrisonerCapacity`  

```csharp
public System.Int32 m_PrisonerCapacity;
```

- `public System.SByte m_PrisonerWellbeing`  

```csharp
public System.SByte m_PrisonerWellbeing;
```

- `public System.SByte m_PrisonerHealth`  

```csharp
public System.SByte m_PrisonerHealth;
```


## Constructors

- `public Prison()`  

```csharp
public Prison();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.Prison>());
		if (GetComponent<ServiceUpgrade>() == null)
		{
			if (GetComponent<CityServiceBuilding>() != null)
			{
				components.Add(ComponentType.ReadWrite<Efficiency>());
			}
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
			if (GetComponent<UniqueObject>() == null)
			{
				components.Add(ComponentType.ReadWrite<ServiceDistrict>());
			}
			if (m_PrisonerCapacity != 0)
			{
				components.Add(ComponentType.ReadWrite<Occupant>());
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PrisonData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.Prison>());
		components.Add(ComponentType.ReadWrite<ServiceDispatch>());
		components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		if (m_PrisonerCapacity != 0)
		{
			components.Add(ComponentType.ReadWrite<Occupant>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		PrisonData componentData = default(PrisonData);
		componentData.m_PrisonVanCapacity = m_PrisonVanCapacity;
		componentData.m_PrisonerCapacity = m_PrisonerCapacity;
		componentData.m_PrisonerWellbeing = m_PrisonerWellbeing;
		componentData.m_PrisonerHealth = m_PrisonerHealth;
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, new UpdateFrameData(3));
	}
```


