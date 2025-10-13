# Game.Tools.ApplyRoutesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyRoutesSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Game.Tools.ApplyRoutesSystem+TypeHandle __TypeHandle;

    public ApplyRoutesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityArchetype m_PathTargetEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Game.Tools.ApplyRoutesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ApplyRoutesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ApplyRoutesSystem()`  

```csharp
[Preserve]
	public ApplyRoutesSystem()
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
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_TempQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Temp>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadOnly<Waypoint>(),
				ComponentType.ReadOnly<Segment>()
			}
		});
		m_PathTargetEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<PathTargetMoved>());
		m_AppliedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		RequireForUpdate(m_TempQuery);
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
		PatchTempReferencesJob jobData = new PatchTempReferencesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaypointType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaypointConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Routes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RW_BufferLookup, ref base.CheckedStateRef)
		};
		HandleTempEntitiesJob jobData2 = new HandleTempEntitiesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaypointType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SegmentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoutePositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Position_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteConnectedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoutePathTargetsType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_PathTargets_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInformationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteWaypointType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_RouteSegmentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoutePositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleTimingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_VehicleTiming_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteInfo_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Waypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_Segments = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferLookup, ref base.CheckedStateRef),
			m_PathTargetEventArchetype = m_PathTargetEventArchetype,
			m_AppliedTypes = m_AppliedTypes,
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		JobHandle job = JobChunkExtensions.Schedule(jobData, m_TempQuery, base.Dependency);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData2, m_TempQuery, base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(job, jobHandle);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
	}
```


## Nested types

- `Game.Tools.ApplyRoutesSystem+PatchTempReferencesJob`  
- `Game.Tools.ApplyRoutesSystem+HandleTempEntitiesJob`  
- `Game.Tools.ApplyRoutesSystem+TypeHandle`  

