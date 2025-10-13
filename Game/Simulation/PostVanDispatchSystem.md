# Game.Simulation.PostVanDispatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PostVanDispatchSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Unity.Entities.EntityQuery m_RequestQuery;
    private Unity.Entities.EntityQuery m_PostConfigurationQuery;
    private Game.Simulation.PostVanDispatchSystem+TypeHandle __TypeHandle;

    public PostVanDispatchSystem();

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

- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostConfigurationQuery;
```

- `private Game.Simulation.PostVanDispatchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PostVanDispatchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PostVanDispatchSystem()`  

```csharp
[Preserve]
	public PostVanDispatchSystem()
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
		m_RequestQuery = GetEntityQuery(ComponentType.ReadOnly<PostVanRequest>(), ComponentType.ReadOnly<UpdateFrame>());
		m_PostConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<PostConfigurationData>());
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
		uint num = (m_SimulationSystem.frameIndex >> 4) & 0x1F;
		uint nextUpdateFrameIndex = (num + 4) & 0x1F;
		NativeQueue<VehicleDispatch> vehicleDispatches = new NativeQueue<VehicleDispatch>(Allocator.TempJob);
		PostVanDispatchJob jobData = new PostVanDispatchJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_DispatchedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_Dispatched_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInformationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_PostVanRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_PostVanRequest_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceRequest_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PostVanRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_PostVanRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceDispatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RO_BufferLookup, ref base.CheckedStateRef),
			m_MailProducerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RW_ComponentLookup, ref base.CheckedStateRef),
			m_MailBoxData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_MailBox_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PostFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PostFacility_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PostVanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PostVan_RW_ComponentLookup, ref base.CheckedStateRef),
			m_UpdateFrameIndex = num,
			m_NextUpdateFrameIndex = nextUpdateFrameIndex,
			m_PostConfigurationData = m_PostConfigurationQuery.GetSingleton<PostConfigurationData>(),
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

- `Game.Simulation.PostVanDispatchSystem+VehicleDispatch`  
- `Game.Simulation.PostVanDispatchSystem+PostVanDispatchJob`  
- `Game.Simulation.PostVanDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.PostVanDispatchSystem+TypeHandle`  

