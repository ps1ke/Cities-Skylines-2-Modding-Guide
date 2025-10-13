# Game.Simulation.NetLaneReservationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetLaneReservationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Game.Simulation.NetLaneReservationSystem+TypeHandle __TypeHandle;

    public NetLaneReservationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Game.Simulation.NetLaneReservationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.NetLaneReservationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetLaneReservationSystem()`  

```csharp
[Preserve]
	public NetLaneReservationSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_LaneQuery = GetEntityQuery(ComponentType.ReadWrite<LaneReservation>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_LaneQuery);
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
		uint index = m_SimulationSystem.frameIndex % 16;
		m_LaneQuery.ResetFilter();
		m_LaneQuery.SetSharedComponentFilter(new UpdateFrame(index));
		ResetLaneReservationsJob jobData = new ResetLaneReservationsJob
		{
			m_LaneReservationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneReservation_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_LaneQuery, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.NetLaneReservationSystem+ResetLaneReservationsJob`  
- `Game.Simulation.NetLaneReservationSystem+TypeHandle`  

