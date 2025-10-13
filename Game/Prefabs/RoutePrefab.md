# Game.Prefabs.RoutePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColored`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RoutePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IColored
{
    public UnityEngine.Material m_Material;
    public System.Single m_Width;
    public System.Single m_SegmentLength;
    public UnityEngine.Color m_Color;
    public System.String m_LocaleID;

    public UnityEngine.Color32 color { get; }

    public RoutePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.Material m_Material`  

```csharp
public UnityEngine.Material m_Material;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Single m_SegmentLength`  

```csharp
public System.Single m_SegmentLength;
```

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public System.String m_LocaleID`  

```csharp
public System.String m_LocaleID;
```


## Properties

- `public UnityEngine.Color32 color { get }`  

```csharp
public UnityEngine.Color32 color { get; }
```


## Constructors

- `public RoutePrefab()`  

```csharp
public RoutePrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		if (components.Contains(ComponentType.ReadWrite<Route>()))
		{
			components.Add(ComponentType.ReadWrite<RouteWaypoint>());
			components.Add(ComponentType.ReadWrite<RouteSegment>());
			components.Add(ComponentType.ReadWrite<Game.Routes.Color>());
			components.Add(ComponentType.ReadWrite<RouteBufferIndex>());
		}
		else if (components.Contains(ComponentType.ReadWrite<Waypoint>()))
		{
			components.Add(ComponentType.ReadWrite<Position>());
			components.Add(ComponentType.ReadWrite<Owner>());
		}
		else if (components.Contains(ComponentType.ReadWrite<Segment>()))
		{
			components.Add(ComponentType.ReadWrite<CurveElement>());
			components.Add(ComponentType.ReadWrite<Owner>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<RouteData>());
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
		HashSet<ComponentType> hashSet2 = new HashSet<ComponentType>();
		HashSet<ComponentType> hashSet3 = new HashSet<ComponentType>();
		HashSet<ComponentType> hashSet4 = new HashSet<ComponentType>();
		hashSet.Add(ComponentType.ReadWrite<Route>());
		hashSet2.Add(ComponentType.ReadWrite<Waypoint>());
		hashSet3.Add(ComponentType.ReadWrite<Waypoint>());
		hashSet3.Add(ComponentType.ReadWrite<Connected>());
		hashSet4.Add(ComponentType.ReadWrite<Segment>());
		for (int i = 0; i < list.Count; i++)
		{
			list[i].GetArchetypeComponents(hashSet);
			list[i].GetArchetypeComponents(hashSet2);
			list[i].GetArchetypeComponents(hashSet3);
			list[i].GetArchetypeComponents(hashSet4);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet2.Add(ComponentType.ReadWrite<Created>());
		hashSet3.Add(ComponentType.ReadWrite<Created>());
		hashSet4.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		hashSet2.Add(ComponentType.ReadWrite<Updated>());
		hashSet3.Add(ComponentType.ReadWrite<Updated>());
		hashSet4.Add(ComponentType.ReadWrite<Updated>());
		RouteData componentData = entityManager.GetComponentData<RouteData>(entity);
		componentData.m_RouteArchetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet));
		componentData.m_WaypointArchetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet2));
		componentData.m_ConnectedArchetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet3));
		componentData.m_SegmentArchetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet4));
		entityManager.SetComponentData(entity, componentData);
	}
```


