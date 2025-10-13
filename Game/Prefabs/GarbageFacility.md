# Game.Prefabs.GarbageFacility

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GarbageFacility : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_GarbageCapacity;
    public System.Int32 m_VehicleCapacity;
    public System.Int32 m_TransportCapacity;
    public System.Int32 m_ProcessingSpeed;
    public System.Boolean m_IndustrialWasteOnly;
    public System.Boolean m_LongTermStorage;

    public GarbageFacility();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_GarbageCapacity`  

```csharp
public System.Int32 m_GarbageCapacity;
```

- `public System.Int32 m_VehicleCapacity`  

```csharp
public System.Int32 m_VehicleCapacity;
```

- `public System.Int32 m_TransportCapacity`  

```csharp
public System.Int32 m_TransportCapacity;
```

- `public System.Int32 m_ProcessingSpeed`  

```csharp
public System.Int32 m_ProcessingSpeed;
```

- `public System.Boolean m_IndustrialWasteOnly`  

```csharp
public System.Boolean m_IndustrialWasteOnly;
```

- `public System.Boolean m_LongTermStorage`  

```csharp
public System.Boolean m_LongTermStorage;
```


## Constructors

- `public GarbageFacility()`  

```csharp
public GarbageFacility();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.GarbageFacility>());
		if (GetComponent<ServiceUpgrade>() == null)
		{
			components.Add(ComponentType.ReadWrite<Resources>());
			if (GetComponent<CityServiceBuilding>() != null)
			{
				components.Add(ComponentType.ReadWrite<GuestVehicle>());
				components.Add(ComponentType.ReadWrite<Efficiency>());
			}
			if (m_VehicleCapacity > 0 || m_TransportCapacity > 0)
			{
				components.Add(ComponentType.ReadWrite<ServiceDispatch>());
				components.Add(ComponentType.ReadWrite<OwnedVehicle>());
			}
			if (GetComponent<UniqueObject>() == null)
			{
				components.Add(ComponentType.ReadWrite<ServiceDistrict>());
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<GarbageFacilityData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.GarbageFacility>());
		components.Add(ComponentType.ReadWrite<Resources>());
		if (m_VehicleCapacity > 0 || m_TransportCapacity > 0)
		{
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		GarbageFacilityData componentData = default(GarbageFacilityData);
		componentData.m_GarbageCapacity = m_GarbageCapacity;
		componentData.m_VehicleCapacity = m_VehicleCapacity;
		componentData.m_TransportCapacity = m_TransportCapacity;
		componentData.m_ProcessingSpeed = m_ProcessingSpeed;
		componentData.m_IndustrialWasteOnly = m_IndustrialWasteOnly;
		componentData.m_LongTermStorage = m_LongTermStorage;
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, new UpdateFrameData(5));
	}
```


