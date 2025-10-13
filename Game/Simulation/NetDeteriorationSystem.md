# Game.Simulation.NetDeteriorationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetDeteriorationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
    private Game.Simulation.NetDeteriorationSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public NetDeteriorationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetMaintenancePriority(Game.Net.NetCondition condition);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
```

- `private Game.Simulation.NetDeteriorationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.NetDeteriorationSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public NetDeteriorationSystem()`  

```csharp
[Preserve]
	public NetDeteriorationSystem()
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

- `public static GetMaintenancePriority(Game.Net.NetCondition condition) : System.Int32`  

```csharp
public static int GetMaintenancePriority(NetCondition condition)
	{
		return (int)(math.cmax(condition.m_Wear) / 10f * 100f) - 10;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_LaneQuery = GetEntityQuery(ComponentType.ReadWrite<LaneCondition>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EdgeQuery = GetEntityQuery(ComponentType.ReadWrite<NetCondition>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_MaintenanceRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<MaintenanceRequest>(), ComponentType.ReadWrite<RequestGroup>());
		RequireAnyForUpdate(m_LaneQuery, m_EdgeQuery);
		Assert.IsTrue((long)(262144 / kUpdatesPerDay) >= 512L);
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
		m_LaneQuery.ResetFilter();
		m_LaneQuery.SetSharedComponentFilter(new UpdateFrame(SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16)));
		m_EdgeQuery.ResetFilter();
		m_EdgeQuery.SetSharedComponentFilter(new UpdateFrame(SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16)));
		UpdateLaneConditionJob jobData = new UpdateLaneConditionJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneDeteriorationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LaneDeteriorationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneConditionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneCondition_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateNetConditionJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_NativeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Native_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_MaintenanceConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_MaintenanceConsumer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetConditionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NetCondition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MaintenanceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_MaintenanceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneConditionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneCondition_RW_ComponentLookup, ref base.CheckedStateRef),
			m_MaintenanceRequestArchetype = m_MaintenanceRequestArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, dependsOn: JobChunkExtensions.ScheduleParallel(jobData, m_LaneQuery, base.Dependency), query: m_EdgeQuery);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.NetDeteriorationSystem+UpdateLaneConditionJob`  
- `Game.Simulation.NetDeteriorationSystem+UpdateNetConditionJob`  
- `Game.Simulation.NetDeteriorationSystem+TypeHandle`  

