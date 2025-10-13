# Game.Rendering.UtilityLodUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UtilityLodUpdateSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_TreeUpdateQuery;
    private Unity.Entities.EntityQuery m_CullingUpdateQuery;
    private Unity.Entities.EntityQuery m_BatchUpdateQuery;
    private System.Boolean m_Loaded;
    private Game.Rendering.UtilityLodUpdateSystem+TypeHandle __TypeHandle;

    public UtilityLodUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_TreeUpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_TreeUpdateQuery;
```

- `private Unity.Entities.EntityQuery m_CullingUpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_CullingUpdateQuery;
```

- `private Unity.Entities.EntityQuery m_BatchUpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_BatchUpdateQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.UtilityLodUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.UtilityLodUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public UtilityLodUpdateSystem()`  

```csharp
[Preserve]
	public UtilityLodUpdateSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_UndergroundViewSystem = base.World.GetOrCreateSystemManaged<UndergroundViewSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_TreeUpdateQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.UtilityLane>(), ComponentType.ReadOnly<LaneGeometry>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Updated>(), ComponentType.Exclude<Deleted>());
		m_CullingUpdateQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.UtilityLane>(), ComponentType.ReadOnly<CullingInfo>(), ComponentType.Exclude<Updated>(), ComponentType.Exclude<Deleted>());
		m_BatchUpdateQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.UtilityLane>(), ComponentType.ReadOnly<MeshBatch>(), ComponentType.Exclude<Updated>(), ComponentType.Exclude<BatchesUpdated>(), ComponentType.Exclude<Deleted>());
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
		UtilityTypes utilityTypes = m_UndergroundViewSystem.utilityTypes;
		base.EntityManager.AddComponent<BatchesUpdated>(m_BatchUpdateQuery);
		JobHandle dependencies;
		Game.Net.SearchSystem.UpdateLaneSearchTreeJob jobData = new Game.Net.SearchSystem.UpdateLaneSearchTreeJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OverriddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UtilityLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLaneGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_Loaded = false,
			m_DilatedUtilityTypes = utilityTypes,
			m_SearchTree = m_NetSearchSystem.GetLaneSearchTree(readOnly: false, out dependencies)
		};
		JobHandle dependencies2;
		PreCullingSystem.InitializeCullingJob jobData2 = new PreCullingSystem.InitializeCullingJob
		{
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Updated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BatchesUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_BatchesUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OverriddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StartNodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EndNodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OrphanType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UtilityLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZoneBlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_Block_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLaneGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionMeshRef = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_UpdateAll = true,
			m_UnspawnedVisible = m_RenderingSystem.unspawnedVisible,
			m_DilatedUtilityTypes = utilityTypes,
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_CullingData = m_PreCullingSystem.GetCullingData(readOnly: false, out dependencies2)
		};
		JobHandle jobHandle = JobChunkExtensions.Schedule(jobData, m_TreeUpdateQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData2, m_CullingUpdateQuery, JobHandle.CombineDependencies(base.Dependency, dependencies2));
		m_NetSearchSystem.AddLaneSearchTreeWriter(jobHandle);
		m_PreCullingSystem.AddCullingDataWriter(jobHandle2);
		m_TerrainSystem.AddCPUHeightReader(jobHandle2);
		base.Dependency = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		m_PreCullingSystem.ResetCulling();
	}
```


## Nested types

- `Game.Rendering.UtilityLodUpdateSystem+TypeHandle`  

