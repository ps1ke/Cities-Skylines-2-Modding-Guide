# Game.Simulation.WorkWatercraftAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WorkWatercraftAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Simulation.WorkWatercraftAISystem+TypeHandle __TypeHandle;

    public WorkWatercraftAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Simulation.WorkWatercraftAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WorkWatercraftAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WorkWatercraftAISystem()`  

```csharp
[Preserve]
	public WorkWatercraftAISystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 8;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_VehicleQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Vehicles.WorkVehicle>(), ComponentType.ReadWrite<WatercraftCurrentLane>(), ComponentType.ReadOnly<Owner>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadWrite<PathOwner>(), ComponentType.ReadWrite<Target>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<TripSource>(), ComponentType.Exclude<OutOfControl>());
		RequireForUpdate(m_VehicleQuery);
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
		NativeQueue<WorkAction> workQueue = new NativeQueue<WorkAction>(Allocator.TempJob);
		WorkWatercraftTickJob jobData = new WorkWatercraftTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInformationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentRouteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_CurrentRoute_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WatercraftType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Watercraft_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_WorkVehicle_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftNavigationLane_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlantData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Plant_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ExtractorFacility_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWatercraftData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WatercraftData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWorkVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TreeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWorkStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkStopData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNavigationAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NavigationAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaypointData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BoardingVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_BoardingVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 64).AsParallelWriter(),
			m_WorkQueue = workQueue.AsParallelWriter()
		};
		WorkWatercraftWorkJob jobData2 = new WorkWatercraftWorkJob
		{
			m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Extractor_RW_ComponentLookup, ref base.CheckedStateRef),
			m_WorkQueue = workQueue
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_VehicleQuery, base.Dependency);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
		workQueue.Dispose(jobHandle2);
		m_PathfindSetupSystem.AddQueueWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.WorkWatercraftAISystem+WorkAction`  
- `Game.Simulation.WorkWatercraftAISystem+WorkWatercraftTickJob`  
- `Game.Simulation.WorkWatercraftAISystem+WorkWatercraftWorkJob`  
- `Game.Simulation.WorkWatercraftAISystem+TypeHandle`  

