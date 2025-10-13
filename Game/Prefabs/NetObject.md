# Game.Prefabs.NetObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.NetPieceRequirements[] m_SetCompositionState;
    public Game.Net.RoadTypes m_RequireRoad;
    public Game.Net.RoadTypes m_RoadPassThrough;
    public Game.Net.TrackTypes m_TrackPassThrough;
    public System.Single m_NodeOffset;
    public System.Boolean m_Attached;

    public NetObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NetPieceRequirements[] m_SetCompositionState`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_SetCompositionState;
```

- `public Game.Net.RoadTypes m_RequireRoad`  

```csharp
public Game.Net.RoadTypes m_RequireRoad;
```

- `public Game.Net.RoadTypes m_RoadPassThrough`  

```csharp
public Game.Net.RoadTypes m_RoadPassThrough;
```

- `public Game.Net.TrackTypes m_TrackPassThrough`  

```csharp
public Game.Net.TrackTypes m_TrackPassThrough;
```

- `public System.Single m_NodeOffset`  

```csharp
public System.Single m_NodeOffset;
```

- `public System.Boolean m_Attached`  

```csharp
public System.Boolean m_Attached;
```


## Constructors

- `public NetObject()`  

```csharp
public NetObject();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Objects.NetObject>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<NetObjectData>());
		components.Add(ComponentType.ReadWrite<PlaceableObjectData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		NetObjectData componentData = default(NetObjectData);
		NetCompositionHelpers.GetRequirementFlags(m_SetCompositionState, out componentData.m_CompositionFlags, out var sectionFlags);
		if (sectionFlags != 0)
		{
			ComponentBase.baseLog.ErrorFormat(base.prefab, "NetObject ({0}) cannot set section flags: {1}", base.prefab.name, sectionFlags);
		}
		componentData.m_RequireRoad = m_RequireRoad;
		componentData.m_RoadPassThrough = m_RoadPassThrough;
		componentData.m_TrackPassThrough = m_TrackPassThrough;
		if (m_RequireRoad == RoadTypes.Car && m_SetCompositionState != null)
		{
			for (int i = 0; i < m_SetCompositionState.Length; i++)
			{
				if (m_SetCompositionState[i] == NetPieceRequirements.ShipStop)
				{
					componentData.m_RequireRoad |= RoadTypes.Watercraft;
				}
			}
		}
		entityManager.SetComponentData(entity, componentData);
		PlaceableObjectData componentData2 = entityManager.GetComponentData<PlaceableObjectData>(entity);
		componentData2.m_Flags |= Game.Objects.PlacementFlags.NetObject;
		componentData2.m_PlacementOffset.z = m_NodeOffset;
		bool flag = (componentData.m_CompositionFlags & CompositionFlags.nodeMask) != default(CompositionFlags);
		bool num = (componentData.m_CompositionFlags & ~CompositionFlags.nodeMask) != default(CompositionFlags);
		if (flag)
		{
			componentData2.m_Flags |= Game.Objects.PlacementFlags.RoadNode;
			componentData2.m_SubReplacementType = SubReplacementType.None;
		}
		if (num || !flag)
		{
			componentData2.m_Flags |= Game.Objects.PlacementFlags.RoadEdge;
			componentData2.m_SubReplacementType = SubReplacementType.None;
		}
		if ((m_RequireRoad & RoadTypes.Watercraft) != RoadTypes.None)
		{
			componentData2.m_Flags |= Game.Objects.PlacementFlags.Waterway;
		}
		if (m_Attached)
		{
			componentData2.m_Flags |= Game.Objects.PlacementFlags.Attached;
		}
		entityManager.SetComponentData(entity, componentData2);
	}
```


