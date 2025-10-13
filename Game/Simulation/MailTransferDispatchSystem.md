# Game.Simulation.MailTransferDispatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MailTransferDispatchSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Unity.Entities.EntityQuery m_RequestQuery;
    private Game.Simulation.MailTransferDispatchSystem+TypeHandle __TypeHandle;

    public MailTransferDispatchSystem();

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

- `private Game.Simulation.MailTransferDispatchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.MailTransferDispatchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MailTransferDispatchSystem()`  

```csharp
[Preserve]
	public MailTransferDispatchSystem()
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
		m_RequestQuery = GetEntityQuery(ComponentType.ReadOnly<MailTransferRequest>(), ComponentType.ReadOnly<UpdateFrame>());
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
		uint num = (m_SimulationSystem.frameIndex >> 4) & 7;
		uint nextUpdateFrameIndex = (num + 4) & 7;
		NativeQueue<DispatchAction> dispatchActions = new NativeQueue<DispatchAction>(Allocator.TempJob);
		MailTransferDispatchJob jobData = new MailTransferDispatchJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_MailTransferRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_MailTransferRequest_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DispatchedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_Dispatched_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInformationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceRequest_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MailTransferRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_MailTransferRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PostFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PostFacility_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceDispatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RO_BufferLookup, ref base.CheckedStateRef),
			m_TripNeededs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_TripNeeded_RO_BufferLookup, ref base.CheckedStateRef),
			m_UpdateFrameIndex = num,
			m_NextUpdateFrameIndex = nextUpdateFrameIndex,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_DispatchActions = dispatchActions.AsParallelWriter(),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 64).AsParallelWriter()
		};
		DispatchActionJob jobData2 = new DispatchActionJob
		{
			m_RequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_MailTransferRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PostFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PostFacility_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceDispatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RW_BufferLookup, ref base.CheckedStateRef),
			m_TripNeededs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RW_BufferLookup, ref base.CheckedStateRef),
			m_DispatchActions = dispatchActions,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_RequestQuery, base.Dependency);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
		dispatchActions.Dispose(jobHandle2);
		m_PathfindSetupSystem.AddQueueWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.MailTransferDispatchSystem+DispatchAction`  
- `Game.Simulation.MailTransferDispatchSystem+MailTransferDispatchJob`  
- `Game.Simulation.MailTransferDispatchSystem+DispatchActionJob`  
- `Game.Simulation.MailTransferDispatchSystem+TypeHandle`  

