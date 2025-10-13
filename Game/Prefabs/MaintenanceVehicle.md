# Game.Prefabs.MaintenanceVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MaintenanceVehicle : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Simulation.MaintenanceType m_MaintenanceType;
    public System.Int32 m_MaintenanceCapacity;
    public System.Int32 m_MaintenanceRate;

    public MaintenanceVehicle();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Simulation.MaintenanceType m_MaintenanceType`  

```csharp
public Game.Simulation.MaintenanceType m_MaintenanceType;
```

- `public System.Int32 m_MaintenanceCapacity`  

```csharp
public System.Int32 m_MaintenanceCapacity;
```

- `public System.Int32 m_MaintenanceRate`  

```csharp
public System.Int32 m_MaintenanceRate;
```


## Constructors

- `public MaintenanceVehicle()`  

```csharp
public MaintenanceVehicle();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Vehicles.MaintenanceVehicle>());
		if (components.Contains(ComponentType.ReadWrite<Moving>()))
		{
			components.Add(ComponentType.ReadWrite<PathInformation>());
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
		}
		if ((m_MaintenanceType & MaintenanceType.Park) != MaintenanceType.None)
		{
			components.Add(ComponentType.ReadWrite<ParkMaintenanceVehicle>());
		}
		if ((m_MaintenanceType & (MaintenanceType.Road | MaintenanceType.Snow | MaintenanceType.Vehicle)) != MaintenanceType.None)
		{
			components.Add(ComponentType.ReadWrite<RoadMaintenanceVehicle>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<MaintenanceVehicleData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new MaintenanceVehicleData(m_MaintenanceType, m_MaintenanceCapacity, m_MaintenanceRate));
		entityManager.SetComponentData(entity, new UpdateFrameData(7));
	}
```


