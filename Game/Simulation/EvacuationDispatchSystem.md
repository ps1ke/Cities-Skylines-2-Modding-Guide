# Game.Simulation.EvacuationDispatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EvacuationDispatchSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Unity.Entities.EntityQuery m_RequestQuery;
    private Game.Simulation.EvacuationDispatchSystem+TypeHandle __TypeHandle;

    public EvacuationDispatchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Unity.Entities.EntityQuery m_RequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequestQuery;
```

- `private Game.Simulation.EvacuationDispatchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.EvacuationDispatchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EvacuationDispatchSystem()`  

```csharp
[Preserve]
	public EvacuationDispatchSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_RequestQuery = GetEntityQuery(ComponentType.ReadOnly<EvacuationRequest>(), ComponentType.ReadOnly<UpdateFrame>());
		RequireForUpdate(m_RequestQuery);
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
		uint num = (m_SimulationSystem.frameIndex >> 4) & 3;
		uint nextUpdateFrameIndex = (num + 4) & 3;
		NativeQueue<VehicleDispatch> vehicleDispatches = new NativeQueue<VehicleDispatch>(Allocator.Persistent);
		EvacuationDispatchJob jobData = new EvacuationDispatchJob
		{
			m_UpdateFrameIndex = num,
			m_NextUpdateFrameIndex = nextUpdateFrameIndex,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_EvacuationRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_EvacuationRequest_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DispatchedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_Dispatched_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInformationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceRequest_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EvacuationRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_EvacuationRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceDispatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RO_BufferLookup, ref base.CheckedStateRef),
			m_InDangerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InDanger_RW_ComponentLookup, ref base.CheckedStateRef),
			m_EmergencyShelterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_EmergencyShelter_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_VehicleDispatches = vehicleDispatches.AsParallelWriter(),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 64).AsParallelWriter()
		};
		DispatchVehiclesJob jobData2 = new DispatchVehiclesJob
		{
			m_VehicleDispatches = vehicleDispatches,
			m_ServiceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ServiceRequest_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceDispatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RW_BufferLookup, ref base.CheckedStateRef)
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_RequestQuery, base.Dependency);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
		vehicleDispatches.Dispose(jobHandle2);
		m_PathfindSetupSystem.AddQueueWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.EvacuationDispatchSystem+VehicleDispatch`  
- `Game.Simulation.EvacuationDispatchSystem+EvacuationDispatchJob`  
- `Game.Simulation.EvacuationDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.EvacuationDispatchSystem+TypeHandle`  

