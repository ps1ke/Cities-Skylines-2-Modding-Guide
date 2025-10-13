# Game.Serialization.InitializeObsoleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeObsoleteSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ObsoleteQuery;
    private Unity.Entities.EntityQuery m_MeshSettingsQuery;
    private System.Collections.Generic.HashSet<Unity.Entities.ComponentType> m_ArchetypeComponents;
    private System.Collections.Generic.Dictionary<System.Type, Game.Prefabs.PrefabBase> m_PrefabInstances;
    private Game.Serialization.InitializeObsoleteSystem+TypeHandle __TypeHandle;

    public InitializeObsoleteSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Entities.EntityArchetype GetArchetype<T>();
    private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType>();
    private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType1, TComponentType2>();
    private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType1, TComponentType2, TComponentType3>();
    private T GetPrefabInstance<T>();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ObsoleteQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObsoleteQuery;
```

- `private Unity.Entities.EntityQuery m_MeshSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshSettingsQuery;
```

- `private System.Collections.Generic.HashSet<Unity.Entities.ComponentType> m_ArchetypeComponents`  

```csharp
private System.Collections.Generic.HashSet<Unity.Entities.ComponentType> m_ArchetypeComponents;
```

- `private System.Collections.Generic.Dictionary<System.Type, Game.Prefabs.PrefabBase> m_PrefabInstances`  

```csharp
private System.Collections.Generic.Dictionary<System.Type, Game.Prefabs.PrefabBase> m_PrefabInstances;
```

- `private Game.Serialization.InitializeObsoleteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.InitializeObsoleteSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeObsoleteSystem()`  

```csharp
[Preserve]
	public InitializeObsoleteSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private GetArchetype<T>() : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype<T>();
```

- `private GetArchetype<T, TComponentType>() : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType>();
```

- `private GetArchetype<T, TComponentType1, TComponentType2>() : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType1, TComponentType2>();
```

- `private GetArchetype<T, TComponentType1, TComponentType2, TComponentType3>() : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype<T, TComponentType1, TComponentType2, TComponentType3>();
```

- `private GetPrefabInstance<T>() : T`  

```csharp
private T GetPrefabInstance<T>();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ObsoleteQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<ObjectData>(),
				ComponentType.ReadOnly<NetData>(),
				ComponentType.ReadOnly<AggregateNetData>(),
				ComponentType.ReadOnly<NetLaneArchetypeData>(),
				ComponentType.ReadOnly<AreaData>()
			},
			Disabled = new ComponentType[1] { ComponentType.ReadOnly<PrefabData>() }
		});
		m_MeshSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<MeshSettingsData>());
		RequireForUpdate(m_ObsoleteQuery);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_ArchetypeComponents = new HashSet<ComponentType>();
		m_PrefabInstances = new Dictionary<Type, PrefabBase>();
		EntityArchetype archetype = GetArchetype<ObjectPrefab>();
		EntityArchetype archetype2 = GetArchetype<StaticObjectPrefab>();
		EntityArchetype archetype3 = GetArchetype<NetGeometryPrefab, Game.Net.Node>();
		EntityArchetype archetype4 = GetArchetype<NetGeometryPrefab, Edge>();
		EntityArchetype archetype5 = GetArchetype<NetGeometryPrefab, NetCompositionData, NetCompositionCrosswalk>();
		EntityArchetype archetype6 = GetArchetype<NetGeometryPrefab, NetCompositionData, NetCompositionLane>();
		EntityArchetype archetype7 = GetArchetype<AggregateNetPrefab>();
		EntityArchetype archetype8 = GetArchetype<LotPrefab, Area>();
		EntityArchetype archetype9 = GetArchetype<DistrictPrefab, Area>();
		EntityArchetype archetype10 = GetArchetype<MapTilePrefab, Area>();
		EntityArchetype archetype11 = GetArchetype<SpacePrefab, Area>();
		EntityArchetype archetype12 = GetArchetype<SurfacePrefab, Area>();
		NetLaneArchetypeData netLaneArchetypeData = default(NetLaneArchetypeData);
		netLaneArchetypeData.m_LaneArchetype = GetArchetype<NetLanePrefab, Lane>();
		netLaneArchetypeData.m_AreaLaneArchetype = GetArchetype<NetLanePrefab, Lane, AreaLane>();
		netLaneArchetypeData.m_EdgeLaneArchetype = GetArchetype<NetLanePrefab, Lane, EdgeLane>();
		netLaneArchetypeData.m_NodeLaneArchetype = GetArchetype<NetLanePrefab, Lane, NodeLane>();
		netLaneArchetypeData.m_EdgeSlaveArchetype = GetArchetype<NetLanePrefab, Lane, SlaveLane, EdgeLane>();
		netLaneArchetypeData.m_NodeSlaveArchetype = GetArchetype<NetLanePrefab, Lane, SlaveLane, NodeLane>();
		netLaneArchetypeData.m_EdgeMasterArchetype = GetArchetype<NetLanePrefab, Lane, MasterLane, EdgeLane>();
		netLaneArchetypeData.m_NodeMasterArchetype = GetArchetype<NetLanePrefab, Lane, MasterLane, NodeLane>();
		foreach (KeyValuePair<Type, PrefabBase> item in m_PrefabInstances)
		{
			UnityEngine.Object.DestroyImmediate(item.Value);
		}
		m_ArchetypeComponents = null;
		m_PrefabInstances = null;
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new InitializeObsoleteJob
		{
			m_StackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AreaGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MovingObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_MovingObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AggregateNetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AggregateNetData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetNameType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetNameData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetArrowType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetArrowData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetLaneArchetypeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetLaneArchetypeData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AreaData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubMeshType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubMesh_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetGeometrySectionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetGeometrySection_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_MeshSettingsData = m_MeshSettingsQuery.GetSingleton<MeshSettingsData>(),
			m_ObjectArchetype = archetype,
			m_ObjectGeometryArchetype = archetype2,
			m_NetGeometryNodeArchetype = archetype3,
			m_NetGeometryEdgeArchetype = archetype4,
			m_NetNodeCompositionArchetype = archetype5,
			m_NetEdgeCompositionArchetype = archetype6,
			m_NetAggregateArchetype = archetype7,
			m_AreaLotArchetype = archetype8,
			m_AreaDistrictArchetype = archetype9,
			m_AreaMapTileArchetype = archetype10,
			m_AreaSpaceArchetype = archetype11,
			m_AreaSurfaceArchetype = archetype12,
			m_NetLaneArchetypeData = netLaneArchetypeData
		}, m_ObsoleteQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Serialization.InitializeObsoleteSystem+InitializeObsoleteJob`  
- `Game.Serialization.InitializeObsoleteSystem+TypeHandle`  

