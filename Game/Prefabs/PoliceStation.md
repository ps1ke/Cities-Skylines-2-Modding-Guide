# Game.Prefabs.PoliceStation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PoliceStation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_PatrolCarCapacity;
    public System.Int32 m_PoliceHelicopterCapacity;
    public System.Int32 m_JailCapacity;
    public Game.Prefabs.PolicePurpose m_Purposes;

    public PoliceStation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_PatrolCarCapacity`  

```csharp
public System.Int32 m_PatrolCarCapacity;
```

- `public System.Int32 m_PoliceHelicopterCapacity`  

```csharp
public System.Int32 m_PoliceHelicopterCapacity;
```

- `public System.Int32 m_JailCapacity`  

```csharp
public System.Int32 m_JailCapacity;
```

- `public Game.Prefabs.PolicePurpose m_Purposes`  

```csharp
public Game.Prefabs.PolicePurpose m_Purposes;
```


## Constructors

- `public PoliceStation()`  

```csharp
public PoliceStation();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.PoliceStation>());
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
			if (m_JailCapacity != 0)
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
		components.Add(ComponentType.ReadWrite<PoliceStationData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.PoliceStation>());
		components.Add(ComponentType.ReadWrite<ServiceDispatch>());
		components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		if (m_JailCapacity != 0)
		{
			components.Add(ComponentType.ReadWrite<Occupant>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		PoliceStationData componentData = default(PoliceStationData);
		componentData.m_PatrolCarCapacity = m_PatrolCarCapacity;
		componentData.m_PoliceHelicopterCapacity = m_PoliceHelicopterCapacity;
		componentData.m_JailCapacity = m_JailCapacity;
		componentData.m_PurposeMask = m_Purposes;
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, new UpdateFrameData(8));
	}
```


