# Game.Prefabs.AircraftPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.VehiclePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class AircraftPrefab : Game.Prefabs.VehiclePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Single m_GroundMaxSpeed;
    public System.Single m_GroundAcceleration;
    public System.Single m_GroundBraking;
    public Unity.Mathematics.float2 m_GroundTurning;

    protected AircraftPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Single m_GroundMaxSpeed`  

```csharp
public System.Single m_GroundMaxSpeed;
```

- `public System.Single m_GroundAcceleration`  

```csharp
public System.Single m_GroundAcceleration;
```

- `public System.Single m_GroundBraking`  

```csharp
public System.Single m_GroundBraking;
```

- `public Unity.Mathematics.float2 m_GroundTurning`  

```csharp
public Unity.Mathematics.float2 m_GroundTurning;
```


## Constructors

- `protected AircraftPrefab()`  

```csharp
protected AircraftPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Aircraft>());
		if (components.Contains(ComponentType.ReadWrite<Stopped>()))
		{
			components.Add(ComponentType.ReadWrite<ParkedCar>());
		}
		if (components.Contains(ComponentType.ReadWrite<Moving>()))
		{
			components.Add(ComponentType.ReadWrite<AircraftNavigation>());
			components.Add(ComponentType.ReadWrite<AircraftNavigationLane>());
			components.Add(ComponentType.ReadWrite<AircraftCurrentLane>());
			components.Add(ComponentType.ReadWrite<PathOwner>());
			components.Add(ComponentType.ReadWrite<PathElement>());
			components.Add(ComponentType.ReadWrite<Target>());
			components.Add(ComponentType.ReadWrite<Blocker>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<AircraftData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new AircraftData
		{
			m_SizeClass = m_SizeClass,
			m_GroundMaxSpeed = m_GroundMaxSpeed / 3.6f,
			m_GroundAcceleration = m_GroundAcceleration,
			m_GroundBraking = m_GroundBraking,
			m_GroundTurning = math.radians(m_GroundTurning)
		});
		entityManager.SetComponentData(entity, new UpdateFrameData(10));
	}
```


