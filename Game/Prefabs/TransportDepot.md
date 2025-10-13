# Game.Prefabs.TransportDepot

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportDepot : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public Game.Prefabs.TransportType m_TransportType;
    public Game.Vehicles.EnergyTypes m_EnergyTypes;
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Int32 m_VehicleCapacity;
    public System.Single m_ProductionDuration;
    public System.Single m_MaintenanceDuration;
    public System.Boolean m_DispatchCenter;

    public TransportDepot();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public Game.Vehicles.EnergyTypes m_EnergyTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyTypes;
```

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Int32 m_VehicleCapacity`  

```csharp
public System.Int32 m_VehicleCapacity;
```

- `public System.Single m_ProductionDuration`  

```csharp
public System.Single m_ProductionDuration;
```

- `public System.Single m_MaintenanceDuration`  

```csharp
public System.Single m_MaintenanceDuration;
```

- `public System.Boolean m_DispatchCenter`  

```csharp
public System.Boolean m_DispatchCenter;
```


## Constructors

- `public TransportDepot()`  

```csharp
public TransportDepot();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.TransportDepot>());
		if (GetComponent<ServiceUpgrade>() == null)
		{
			if (GetComponent<CityServiceBuilding>() != null)
			{
				components.Add(ComponentType.ReadWrite<Efficiency>());
			}
			if (m_TransportType == TransportType.Taxi)
			{
				components.Add(ComponentType.ReadWrite<ServiceDistrict>());
			}
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<TransportDepotData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.TransportDepot>());
		components.Add(ComponentType.ReadWrite<ServiceDispatch>());
		components.Add(ComponentType.ReadWrite<OwnedVehicle>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		TransportDepotData componentData = default(TransportDepotData);
		componentData.m_TransportType = m_TransportType;
		componentData.m_DispatchCenter = m_DispatchCenter;
		componentData.m_EnergyTypes = m_EnergyTypes;
		componentData.m_SizeClass = m_SizeClass;
		componentData.m_VehicleCapacity = m_VehicleCapacity;
		componentData.m_ProductionDuration = m_ProductionDuration;
		componentData.m_MaintenanceDuration = m_MaintenanceDuration;
		if (m_SizeClass == SizeClass.Undefined)
		{
			componentData.m_SizeClass = ((m_TransportType != TransportType.Taxi) ? SizeClass.Large : SizeClass.Small);
		}
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, new UpdateFrameData(2));
	}
```


