# Game.Prefabs.NetLanePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetLanePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PathfindPrefab m_PathfindPrefab;

    public NetLanePrefab();

    private Unity.Entities.EntityArchetype CreateArchetype(Unity.Entities.EntityManager entityManager, System.Collections.Generic.List<Game.Prefabs.ComponentBase> unityComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> laneComponents);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PathfindPrefab m_PathfindPrefab`  

```csharp
public Game.Prefabs.PathfindPrefab m_PathfindPrefab;
```


## Constructors

- `public NetLanePrefab()`  

```csharp
public NetLanePrefab();
```


## Methods

- `private CreateArchetype(Unity.Entities.EntityManager entityManager, System.Collections.Generic.List<Game.Prefabs.ComponentBase> unityComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> laneComponents) : Unity.Entities.EntityArchetype`  

```csharp
private EntityArchetype CreateArchetype(EntityManager entityManager, List<ComponentBase> unityComponents, HashSet<ComponentType> laneComponents)
	{
		for (int i = 0; i < unityComponents.Count; i++)
		{
			unityComponents[i].GetArchetypeComponents(laneComponents);
		}
		laneComponents.Add(ComponentType.ReadWrite<Created>());
		laneComponents.Add(ComponentType.ReadWrite<Updated>());
		EntityArchetype result = entityManager.CreateArchetype(PrefabUtils.ToArray(laneComponents));
		laneComponents.Clear();
		return result;
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Curve>());
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_PathfindPrefab != null)
		{
			prefabs.Add(m_PathfindPrefab);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<NetLaneData>());
		components.Add(ComponentType.ReadWrite<NetLaneArchetypeData>());
		if (!base.prefab.Has<SecondaryLane>())
		{
			components.Add(ComponentType.ReadWrite<SecondaryNetLane>());
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		List<ComponentBase> list = new List<ComponentBase>();
		GetComponents(list);
		HashSet<ComponentType> hashSet = new HashSet<ComponentType>();
		hashSet.Add(ComponentType.ReadWrite<Lane>());
		NetLaneArchetypeData componentData = default(NetLaneArchetypeData);
		componentData.m_LaneArchetype = CreateArchetype(entityManager, list, hashSet);
		hashSet.Add(ComponentType.ReadWrite<Lane>());
		hashSet.Add(ComponentType.ReadWrite<AreaLane>());
		componentData.m_AreaLaneArchetype = CreateArchetype(entityManager, list, hashSet);
		hashSet.Add(ComponentType.ReadWrite<Lane>());
		hashSet.Add(ComponentType.ReadWrite<EdgeLane>());
		componentData.m_EdgeLaneArchetype = CreateArchetype(entityManager, list, hashSet);
		hashSet.Add(ComponentType.ReadWrite<Lane>());
		hashSet.Add(ComponentType.ReadWrite<NodeLane>());
		componentData.m_NodeLaneArchetype = CreateArchetype(entityManager, list, hashSet);
		hashSet.Add(ComponentType.ReadWrite<Lane>());
		hashSet.Add(ComponentType.ReadWrite<SlaveLane>());
		hashSet.Add(ComponentType.ReadWrite<EdgeLane>());
		componentData.m_EdgeSlaveArchetype = CreateArchetype(entityManager, list, hashSet);
		hashSet.Add(ComponentType.ReadWrite<Lane>());
		hashSet.Add(ComponentType.ReadWrite<SlaveLane>());
		hashSet.Add(ComponentType.ReadWrite<NodeLane>());
		componentData.m_NodeSlaveArchetype = CreateArchetype(entityManager, list, hashSet);
		hashSet.Add(ComponentType.ReadWrite<Lane>());
		hashSet.Add(ComponentType.ReadWrite<MasterLane>());
		hashSet.Add(ComponentType.ReadWrite<EdgeLane>());
		componentData.m_EdgeMasterArchetype = CreateArchetype(entityManager, list, hashSet);
		hashSet.Add(ComponentType.ReadWrite<Lane>());
		hashSet.Add(ComponentType.ReadWrite<MasterLane>());
		hashSet.Add(ComponentType.ReadWrite<NodeLane>());
		componentData.m_NodeMasterArchetype = CreateArchetype(entityManager, list, hashSet);
		entityManager.SetComponentData(entity, componentData);
	}
```


