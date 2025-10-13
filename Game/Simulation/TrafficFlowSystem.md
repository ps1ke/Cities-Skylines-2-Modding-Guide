# Game.Simulation.TrafficFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficFlowSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_RoadQuery;
    private Game.Simulation.TrafficFlowSystem+TypeHandle __TypeHandle;
    public static const System.Int32 UPDATES_PER_DAY;

    public TrafficFlowSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_RoadQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadQuery;
```

- `private Game.Simulation.TrafficFlowSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrafficFlowSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 UPDATES_PER_DAY`  

```csharp
public static const System.Int32 UPDATES_PER_DAY;
```


## Constructors

- `public TrafficFlowSystem()`  

```csharp
[Preserve]
	public TrafficFlowSystem()
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
		return 512;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_LaneQuery = GetEntityQuery(ComponentType.ReadWrite<LaneFlow>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_RoadQuery = GetEntityQuery(ComponentType.ReadWrite<Road>(), ComponentType.ReadOnly<SubLane>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireAnyForUpdate(m_LaneQuery, m_RoadQuery);
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
		float num = m_TimeSystem.normalizedTime * 4f;
		float4 x = new float4(math.max(num - 3f, 1f - num), 1f - math.abs(num - new float3(1f, 2f, 3f)));
		x = math.saturate(x);
		FlowAction action = new FlowAction(Allocator.Persistent);
		m_LaneQuery.ResetFilter();
		m_LaneQuery.SetSharedComponentFilter(new UpdateFrame(SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, 32, 16)));
		m_RoadQuery.ResetFilter();
		m_RoadQuery.SetSharedComponentFilter(new UpdateFrame(SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, 32, 16)));
		UpdateLaneFlowJob jobData = new UpdateLaneFlowJob
		{
			m_TimeFactors = x,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_LaneFlowType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneFlow_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateRoadFlowJob
		{
			m_TimeFactors = x,
			m_SubLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_LaneFlowData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneFlow_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_RoadType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Road_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_FlowActions = action.m_FlowData.AsParallelWriter()
		}, dependsOn: JobChunkExtensions.ScheduleParallel(jobData, m_LaneQuery, base.Dependency), query: m_RoadQuery);
		m_PathfindQueueSystem.Enqueue(action, jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.TrafficFlowSystem+UpdateLaneFlowJob`  
- `Game.Simulation.TrafficFlowSystem+UpdateRoadFlowJob`  
- `Game.Simulation.TrafficFlowSystem+TypeHandle`  

