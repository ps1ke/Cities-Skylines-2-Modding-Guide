# Game.Rendering.BatchInstanceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatchInstanceSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.BatchInstanceSystem+Groups m_Groups;
    private Game.Rendering.BatchInstanceSystem+TypeHandle __TypeHandle;

    public BatchInstanceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.BatchInstanceSystem+Groups m_Groups`  

```csharp
private Game.Rendering.BatchInstanceSystem+Groups m_Groups;
```

- `private Game.Rendering.BatchInstanceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BatchInstanceSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BatchInstanceSystem()`  

```csharp
[Preserve]
	public BatchInstanceSystem()
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
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
		m_UndergroundViewSystem = base.World.GetOrCreateSystemManaged<UndergroundViewSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_Groups = base.World.GetOrCreateSystemManaged<Groups>();
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
		JobHandle dependencies;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: true, out dependencies);
		m_Groups.m_GroupActionQueue = new NativeParallelQueue<GroupActionData>(Allocator.TempJob);
		m_Groups.m_VelocityQueue = new NativeQueue<VelocityData>(Allocator.TempJob);
		m_Groups.m_FadeQueue = new NativeQueue<FadeData>(Allocator.TempJob);
		JobHandle dependencies2;
		BatchInstanceJob jobData = new BatchInstanceJob
		{
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ErrorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Error_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WarningData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Warning_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OverrideData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Override_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HighlightedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Highlighted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshBatch_RW_BufferLookup, ref base.CheckedStateRef),
			m_FadeBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_FadeBatch_RW_BufferLookup, ref base.CheckedStateRef),
			m_StoppedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stopped_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnspawnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_NetObject_RO_ComponentLookup, ref base.CheckedStateRef),
			m_QuantityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Quantity_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectMarkerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Marker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RelativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Relative_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnderConstructionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformFrames = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OrphanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetOutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetMarkerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Marker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CutRanges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_CutRange_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_ZoneBlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGrowthScaleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GrowthScaleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabQuantityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_QuantityObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionMeshRef = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabBatchGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_BatchGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_MarkersVisible = m_RenderingSystem.markersVisible,
			m_UnspawnedVisible = m_RenderingSystem.unspawnedVisible,
			m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_UseLodFade = m_RenderingSystem.lodCrossFade,
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_DilatedUtilityTypes = m_UndergroundViewSystem.utilityTypes,
			m_VisibleMask = m_PreCullingSystem.visibleMask,
			m_BecameVisible = m_PreCullingSystem.becameVisible,
			m_BecameHidden = m_PreCullingSystem.becameHidden,
			m_BatchInstances = nativeBatchInstances,
			m_CullingData = m_PreCullingSystem.GetUpdatedData(readOnly: true, out dependencies2),
			m_GroupActionQueue = m_Groups.m_GroupActionQueue.AsWriter(),
			m_VelocityQueue = m_Groups.m_VelocityQueue.AsParallelWriter(),
			m_FadeQueue = m_Groups.m_FadeQueue.AsParallelWriter()
		};
		JobHandle jobHandle = jobData.Schedule(jobData.m_CullingData, 4, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
		m_BatchManagerSystem.AddNativeBatchInstancesReader(jobHandle);
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		m_Groups.m_Dependency = jobHandle;
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Rendering.BatchInstanceSystem+Groups`  
- `Game.Rendering.BatchInstanceSystem+BatchInstanceJob`  
- `Game.Rendering.BatchInstanceSystem+GroupActionData`  
- `Game.Rendering.BatchInstanceSystem+VelocityData`  
- `Game.Rendering.BatchInstanceSystem+FadeData`  
- `Game.Rendering.BatchInstanceSystem+DequeueFadesJob`  
- `Game.Rendering.BatchInstanceSystem+GroupActionJob`  
- `Game.Rendering.BatchInstanceSystem+TypeHandle`  

