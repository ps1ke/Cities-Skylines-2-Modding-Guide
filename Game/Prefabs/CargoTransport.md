# Game.Prefabs.CargoTransport

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CargoTransport : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_CargoCapacity;
    public System.Int32 m_MaxResourceCount;
    public System.Single m_MaintenanceRange;
    public Game.Economy.ResourceInEditor[] m_TransportedResources;

    public CargoTransport();

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

- `public System.Int32 m_MaxResourceCount`  

```csharp
public System.Int32 m_MaxResourceCount;
```

- `public System.Single m_MaintenanceRange`  

```csharp
public System.Single m_MaintenanceRange;
```

- `public Game.Economy.ResourceInEditor[] m_TransportedResources`  

```csharp
public Game.Economy.ResourceInEditor[] m_TransportedResources;
```


## Constructors

- `public CargoTransport()`  

```csharp
public CargoTransport();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Vehicles.CargoTransport>());
		components.Add(ComponentType.ReadWrite<Resources>());
		components.Add(ComponentType.ReadWrite<LoadingResources>());
		components.Add(ComponentType.ReadWrite<Odometer>());
		if (components.Contains(ComponentType.ReadWrite<Moving>()) && (!components.Contains(ComponentType.ReadWrite<Controller>()) || components.Contains(ComponentType.ReadWrite<LayoutElement>())))
		{
			components.Add(ComponentType.ReadWrite<PathInformation>());
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<CargoTransportVehicleData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		Resource resource = Resource.NoResource;
		if (m_TransportedResources != null)
		{
			for (int i = 0; i < m_TransportedResources.Length; i++)
			{
				resource |= EconomyUtils.GetResource(m_TransportedResources[i]);
			}
		}
		entityManager.SetComponentData(entity, new CargoTransportVehicleData(resource, m_CargoCapacity, m_MaxResourceCount, m_MaintenanceRange * 1000f));
	}
```


