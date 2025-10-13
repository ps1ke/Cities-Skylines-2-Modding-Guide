# Game.Prefabs.TrainPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.VehiclePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ExcludeGeneratedModTag`  

## Code

```csharp
public abstract class TrainPrefab : Game.Prefabs.VehiclePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Net.TrackTypes m_TrackType;
    public Game.Vehicles.EnergyTypes m_EnergyType;
    public System.Single m_MaxSpeed;
    public System.Single m_Acceleration;
    public System.Single m_Braking;
    public Unity.Mathematics.float2 m_Turning;
    public Unity.Mathematics.float2 m_BogieOffset;
    public Unity.Mathematics.float2 m_AttachOffset;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    protected TrainPrefab();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    protected virtual System.Void RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Net.TrackTypes m_TrackType`  

```csharp
public Game.Net.TrackTypes m_TrackType;
```

- `public Game.Vehicles.EnergyTypes m_EnergyType`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyType;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_Acceleration`  

```csharp
public System.Single m_Acceleration;
```

- `public System.Single m_Braking`  

```csharp
public System.Single m_Braking;
```

- `public Unity.Mathematics.float2 m_Turning`  

```csharp
public Unity.Mathematics.float2 m_Turning;
```

- `public Unity.Mathematics.float2 m_BogieOffset`  

```csharp
public Unity.Mathematics.float2 m_BogieOffset;
```

- `public Unity.Mathematics.float2 m_AttachOffset`  

```csharp
public Unity.Mathematics.float2 m_AttachOffset;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `protected TrainPrefab()`  

```csharp
protected TrainPrefab();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Train>());
		if (components.Contains(ComponentType.ReadWrite<Stopped>()))
		{
			components.Add(ComponentType.ReadWrite<ParkedTrain>());
		}
		if (components.Contains(ComponentType.ReadWrite<Moving>()))
		{
			components.Add(ComponentType.ReadWrite<TrainNavigation>());
			components.Add(ComponentType.ReadWrite<TrainCurrentLane>());
			components.Add(ComponentType.ReadWrite<TrainBogieFrame>());
			if (components.Contains(ComponentType.ReadWrite<LayoutElement>()))
			{
				components.Add(ComponentType.ReadWrite<PathOwner>());
				components.Add(ComponentType.ReadWrite<PathElement>());
				components.Add(ComponentType.ReadWrite<Target>());
				components.Add(ComponentType.ReadWrite<Blocker>());
				components.Add(ComponentType.ReadWrite<TrainNavigationLane>());
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TrainData>());
		components.Add(ComponentType.ReadWrite<TrainObjectData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new UpdateFrameData(3));
	}
```

- `protected virtual RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RefreshArchetype(EntityManager entityManager, Entity entity)
	{
		List<ComponentBase> list = new List<ComponentBase>();
		GetComponents(list);
		ObjectData componentData = default(ObjectData);
		MovingObjectData componentData2 = default(MovingObjectData);
		TrainObjectData componentData3 = default(TrainObjectData);
		HashSet<ComponentType> hashSet = new HashSet<ComponentType>();
		hashSet.Add(ComponentType.ReadWrite<Controller>());
		hashSet.Add(ComponentType.ReadWrite<Moving>());
		for (int i = 0; i < list.Count; i++)
		{
			list[i].GetArchetypeComponents(hashSet);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		componentData.m_Archetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet));
		hashSet.Clear();
		hashSet.Add(ComponentType.ReadWrite<Controller>());
		hashSet.Add(ComponentType.ReadWrite<Stopped>());
		for (int j = 0; j < list.Count; j++)
		{
			list[j].GetArchetypeComponents(hashSet);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		componentData2.m_StoppedArchetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet));
		hashSet.Clear();
		hashSet.Add(ComponentType.ReadWrite<Controller>());
		hashSet.Add(ComponentType.ReadWrite<Moving>());
		hashSet.Add(ComponentType.ReadWrite<LayoutElement>());
		for (int k = 0; k < list.Count; k++)
		{
			list[k].GetArchetypeComponents(hashSet);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		componentData3.m_ControllerArchetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet));
		hashSet.Clear();
		hashSet.Add(ComponentType.ReadWrite<Controller>());
		hashSet.Add(ComponentType.ReadWrite<Stopped>());
		hashSet.Add(ComponentType.ReadWrite<LayoutElement>());
		for (int l = 0; l < list.Count; l++)
		{
			list[l].GetArchetypeComponents(hashSet);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		componentData3.m_StoppedControllerArchetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet));
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, componentData2);
		entityManager.SetComponentData(entity, componentData3);
	}
```


## Nested types

- `Game.Prefabs.TrainPrefab+<get_modTags>d__13`  

