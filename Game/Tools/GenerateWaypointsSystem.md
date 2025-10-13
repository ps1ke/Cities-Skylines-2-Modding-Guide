# Game.Tools.GenerateWaypointsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateWaypointsSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Game.Tools.GenerateWaypointsSystem+TypeHandle __TypeHandle;

    public GenerateWaypointsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Game.Tools.GenerateWaypointsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateWaypointsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateWaypointsSystem()`  

```csharp
[Preserve]
	public GenerateWaypointsSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier1>();
		m_DefinitionQuery = GetEntityQuery(ComponentType.ReadOnly<CreationDefinition>(), ComponentType.ReadOnly<WaypointDefinition>(), ComponentType.ReadOnly<Updated>());
		m_DeletedQuery = GetEntityQuery(ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Segment>(), ComponentType.ReadOnly<Owner>(), ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<PrefabRef>());
		RequireForUpdate(m_DefinitionQuery);
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> definitionChunks = m_DefinitionQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle outJobHandle2;
		NativeList<ArchetypeChunk> deletedChunks = m_DeletedQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2);
		JobHandle jobHandle = IJobExtensions.Schedule(new CreateWaypointsJob
		{
			m_DefinitionChunks = definitionChunks,
			m_DeletedChunks = deletedChunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SegmentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaypointDefinitionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_WaypointDefinition_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SegmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathTargetsData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_PathTargets_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteSegments = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferLookup, ref base.CheckedStateRef),
			m_PathElementData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle, outJobHandle2));
		definitionChunks.Dispose(jobHandle);
		deletedChunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Tools.GenerateWaypointsSystem+CreateWaypointsJob`  
- `Game.Tools.GenerateWaypointsSystem+TypeHandle`  

