# Game.Rendering.RequiredBatchesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RequiredBatchesSystem : Game.GameSystemBase
{
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private System.Boolean m_Loaded;
    private Game.Rendering.RequiredBatchesSystem+TypeHandle __TypeHandle;

    public RequiredBatchesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.RequiredBatchesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.RequiredBatchesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RequiredBatchesSystem()`  

```csharp
[Preserve]
	public RequiredBatchesSystem()
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

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<MeshBatch>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<BatchesUpdated>()
			}
		});
		m_AllQuery = GetEntityQuery(ComponentType.ReadOnly<MeshBatch>(), ComponentType.ReadOnly<PrefabRef>());
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityQuery query = (GetLoaded() ? m_AllQuery : m_UpdatedQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			JobHandle dependencies;
			JobHandle dependencies2;
			JobHandle dependencies3;
			JobHandle jobHandle = JobChunkExtensions.Schedule(new RequiredBatchesJob
			{
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StoppedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stopped_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Object_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ElevationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ObjectMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OrphanType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UtilityLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NetMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_Block_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ErrorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Error_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WarningType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Warning_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OverrideType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Override_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HighlightedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Highlighted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MeshGroupType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCompositionMeshRef = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RW_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RW_BufferLookup, ref base.CheckedStateRef),
				m_PrefabLodMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LodMesh_RW_BufferLookup, ref base.CheckedStateRef),
				m_PrefabMeshMaterials = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_MeshMaterial_RW_BufferLookup, ref base.CheckedStateRef),
				m_PrefabMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MeshData_RW_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCompositionMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshData_RW_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabZoneBlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneBlockData_RW_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBatchGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_BatchGroup_RW_BufferLookup, ref base.CheckedStateRef),
				m_NativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: false, out dependencies),
				m_NativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: false, out dependencies2),
				m_NativeSubBatches = m_BatchManagerSystem.GetNativeSubBatches(readOnly: false, out dependencies3)
			}, query, JobHandle.CombineDependencies(base.Dependency, JobHandle.CombineDependencies(dependencies, dependencies2, dependencies3)));
			m_BatchManagerSystem.AddNativeBatchInstancesWriter(jobHandle);
			m_BatchManagerSystem.AddNativeBatchGroupsWriter(jobHandle);
			m_BatchManagerSystem.AddNativeSubBatchesWriter(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Rendering.RequiredBatchesSystem+RequiredBatchesJob`  
- `Game.Rendering.RequiredBatchesSystem+TypeHandle`  

