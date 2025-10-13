# Game.Prefabs.WorkVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WorkVehicle : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Vehicles.VehicleWorkType m_WorkType;
    public Game.Areas.MapFeature m_MapFeature;
    public Game.Economy.ResourceInEditor[] m_Resources;
    public System.Single m_MaxWorkAmount;

    public WorkVehicle();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Vehicles.VehicleWorkType m_WorkType`  

```csharp
public Game.Vehicles.VehicleWorkType m_WorkType;
```

- `public Game.Areas.MapFeature m_MapFeature`  

```csharp
public Game.Areas.MapFeature m_MapFeature;
```

- `public Game.Economy.ResourceInEditor[] m_Resources`  

```csharp
public Game.Economy.ResourceInEditor[] m_Resources;
```

- `public System.Single m_MaxWorkAmount`  

```csharp
public System.Single m_MaxWorkAmount;
```


## Constructors

- `public WorkVehicle()`  

```csharp
public WorkVehicle();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Vehicles.WorkVehicle>());
		components.Add(ComponentType.ReadWrite<PathInformation>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<WorkVehicleData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		Resource resource = Resource.NoResource;
		if (m_Resources != null)
		{
			for (int i = 0; i < m_Resources.Length; i++)
			{
				resource |= EconomyUtils.GetResource(m_Resources[i]);
			}
		}
		WorkVehicleData componentData = default(WorkVehicleData);
		componentData.m_WorkType = m_WorkType;
		componentData.m_MapFeature = m_MapFeature;
		componentData.m_MaxWorkAmount = m_MaxWorkAmount;
		componentData.m_Resources = resource;
		entityManager.SetComponentData(entity, componentData);
		if (entityManager.HasComponent<CarData>(entity))
		{
			entityManager.SetComponentData(entity, new UpdateFrameData(12));
		}
	}
```


