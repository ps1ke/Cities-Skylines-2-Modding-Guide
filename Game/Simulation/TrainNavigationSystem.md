# Game.Simulation.TrainNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrainNavigationSystem : Game.GameSystemBase
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
    private Game.Simulation.TrainNavigationSystem+TypeHandle __TypeHandle;

    public TrainNavigationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  

```csharp
private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
```

- `private Game.Simulation.TrainNavigationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrainNavigationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TrainNavigationSystem()`  

```csharp
[Preserve]
	public TrainNavigationSystem()
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
		return 3;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_VehicleQuery = GetEntityQuery(ComponentType.ReadOnly<Train>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.ReadOnly<Moving>(), ComponentType.ReadOnly<Target>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<PathElement>(), ComponentType.ReadWrite<PathOwner>(), ComponentType.ReadWrite<TrainCurrentLane>(), ComponentType.ReadWrite<TrainNavigation>(), ComponentType.ReadWrite<TrainNavigationLane>(), ComponentType.ReadWrite<LayoutElement>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<TripSource>());
		m_LaneObjectUpdater = new LaneObjectUpdater(this);
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
		NativeQueue<TrainNavigationHelpers.LaneEffects> laneEffectsQueue = new NativeQueue<TrainNavigationHelpers.LaneEffects>(Allocator.TempJob);
		NativeQueue<TrainNavigationHelpers.LaneSignal> laneSignalQueue = new NativeQueue<TrainNavigationHelpers.LaneSignal>(Allocator.TempJob);
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_VehicleQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle dependencies;
		UpdateNavigationJob jobData = new UpdateNavigationJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LayoutElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BlockerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Blocker_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OdometerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Odometer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainNavigationLane_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NavigationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainNavigation_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Car_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CreatureData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneReservationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneReservation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneSignalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneSignal_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSideEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_VehicleSideEffectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Lanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneOverlaps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_LaneObjectBuffer = m_LaneObjectUpdater.Begin(Allocator.TempJob),
			m_LaneEffects = laneEffectsQueue.AsParallelWriter(),
			m_LaneSignals = laneSignalQueue.AsParallelWriter()
		};
		UpdateLaneReservationsJob jobData2 = new UpdateLaneReservationsJob
		{
			m_Chunks = chunks,
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LayoutType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneReservationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneReservation_RW_ComponentLookup, ref base.CheckedStateRef),
			m_NavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainNavigationLane_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		ApplyLaneEffectsJob jobData3 = new ApplyLaneEffectsJob
		{
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneDeteriorationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LaneDeteriorationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PollutionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Pollution_RW_ComponentLookup, ref base.CheckedStateRef),
			m_LaneConditionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneCondition_RW_ComponentLookup, ref base.CheckedStateRef),
			m_LaneFlowData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneFlow_RW_ComponentLookup, ref base.CheckedStateRef),
			m_LaneEffectsQueue = laneEffectsQueue
		};
		UpdateLaneSignalsJob jobData4 = new UpdateLaneSignalsJob
		{
			m_LaneSignalQueue = laneSignalQueue,
			m_LaneSignalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneSignal_RW_ComponentLookup, ref base.CheckedStateRef)
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_VehicleQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(jobHandle, outJobHandle));
		JobHandle jobHandle3 = IJobExtensions.Schedule(jobData3, jobHandle);
		JobHandle jobHandle4 = IJobExtensions.Schedule(jobData4, jobHandle);
		laneEffectsQueue.Dispose(jobHandle3);
		laneSignalQueue.Dispose(jobHandle4);
		chunks.Dispose(jobHandle2);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		JobHandle job = m_LaneObjectUpdater.Apply(this, jobHandle);
		base.Dependency = JobUtils.CombineDependencies(job, jobHandle2, jobHandle4, jobHandle3);
	}
```


## Nested types

- `Game.Simulation.TrainNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.TrainNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.TrainNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.TrainNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.TrainNavigationSystem+TypeHandle`  

