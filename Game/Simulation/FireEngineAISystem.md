# Game.Simulation.FireEngineAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FireEngineAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityArchetype m_FireRescueRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes;
    private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
    private Game.Simulation.FireEngineAISystem+TypeHandle __TypeHandle;

    public FireEngineAISystem();

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

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_FireRescueRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_FireRescueRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes;
```

- `private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData`  

```csharp
private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
```

- `private Game.Simulation.FireEngineAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FireEngineAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FireEngineAISystem()`  

```csharp
[Preserve]
	public FireEngineAISystem()
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
		return 4;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_VehicleQuery = GetEntityQuery(ComponentType.ReadWrite<CarCurrentLane>(), ComponentType.ReadOnly<Owner>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadWrite<PathOwner>(), ComponentType.ReadWrite<Game.Vehicles.FireEngine>(), ComponentType.ReadWrite<Target>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<TripSource>(), ComponentType.Exclude<OutOfControl>());
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<FireConfigurationData>());
		m_FireRescueRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<FireRescueRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_HandleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<HandleRequest>(), ComponentType.ReadWrite<Game.Common.Event>());
		m_MovingToParkedCarRemoveTypes = new ComponentTypeSet(new ComponentType[13]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<Swaying>(),
			ComponentType.ReadWrite<CarNavigation>(),
			ComponentType.ReadWrite<CarNavigationLane>(),
			ComponentType.ReadWrite<CarCurrentLane>(),
			ComponentType.ReadWrite<PathOwner>(),
			ComponentType.ReadWrite<Target>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<PathElement>(),
			ComponentType.ReadWrite<PathInformation>(),
			ComponentType.ReadWrite<ServiceDispatch>()
		});
		m_MovingToParkedAddTypes = new ComponentTypeSet(ComponentType.ReadWrite<ParkedCar>(), ComponentType.ReadWrite<Stopped>(), ComponentType.ReadWrite<Updated>());
		m_StructuralIntegrityData = new EventHelpers.StructuralIntegrityData(this);
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
		FireConfigurationData singleton = m_ConfigQuery.GetSingleton<FireConfigurationData>();
		NativeQueue<FireExtinguishing> extinguishingQueue = new NativeQueue<FireExtinguishing>(Allocator.TempJob);
		m_StructuralIntegrityData.Update(this, singleton);
		JobHandle dependencies;
		FireEngineTickJob jobData = new FireEngineTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInformationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StoppedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stopped_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FireEngineType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_FireEngine_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Car_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_CarNavigationLane_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ServiceDispatchType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarageLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_GarageLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabFireEngineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_FireEngineData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FireRescueRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_FireRescueRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OnFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RescueTargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_RescueTarget_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FireStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_FireStation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnspawnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneOverlaps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_FireRescueRequestArchetype = m_FireRescueRequestArchetype,
			m_HandleRequestArchetype = m_HandleRequestArchetype,
			m_MovingToParkedCarRemoveTypes = m_MovingToParkedCarRemoveTypes,
			m_MovingToParkedAddTypes = m_MovingToParkedAddTypes,
			m_SimulationFrameIndex = m_SimulationSystem.frameIndex,
			m_RandomSeed = RandomSeed.Next(),
			m_StructuralIntegrityData = m_StructuralIntegrityData,
			m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 64).AsParallelWriter(),
			m_ExtinguishingQueue = extinguishingQueue.AsParallelWriter()
		};
		FireExtinguishingJob jobData2 = new FireExtinguishingJob
		{
			m_OnFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RW_ComponentLookup, ref base.CheckedStateRef),
			m_RescueTargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_RescueTarget_RW_ComponentLookup, ref base.CheckedStateRef),
			m_DamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RW_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ExtinguishingQueue = extinguishingQueue
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_VehicleQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
		extinguishingQueue.Dispose(jobHandle2);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_PathfindSetupSystem.AddQueueWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.FireEngineAISystem+FireExtinguishing`  
- `Game.Simulation.FireEngineAISystem+FireEngineTickJob`  
- `Game.Simulation.FireEngineAISystem+FireExtinguishingJob`  
- `Game.Simulation.FireEngineAISystem+TypeHandle`  

