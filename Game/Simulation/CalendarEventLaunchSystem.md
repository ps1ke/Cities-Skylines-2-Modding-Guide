# Game.Simulation.CalendarEventLaunchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CalendarEventLaunchSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Unity.Entities.EntityQuery m_CalendarEventQuery;
    private Game.Simulation.CalendarEventLaunchSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATES_PER_DAY;

    public CalendarEventLaunchSystem();

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

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Unity.Entities.EntityQuery m_CalendarEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_CalendarEventQuery;
```

- `private Game.Simulation.CalendarEventLaunchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CalendarEventLaunchSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATES_PER_DAY`  

```csharp
private static const System.Int32 UPDATES_PER_DAY;
```


## Constructors

- `public CalendarEventLaunchSystem()`  

```csharp
[Preserve]
	public CalendarEventLaunchSystem()
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
		return 65536;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CalendarEventQuery = GetEntityQuery(ComponentType.ReadOnly<CalendarEventData>());
		GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		RequireForUpdate(m_CalendarEventQuery);
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
		CalendarEventMonths month = (CalendarEventMonths)(1 << Mathf.FloorToInt(m_TimeSystem.normalizedDate * 12f));
		CalendarEventTimes time = (CalendarEventTimes)(1 << Mathf.FloorToInt(m_TimeSystem.normalizedTime * 4f));
		CheckEventLaunchJob jobData = new CheckEventLaunchJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_EventType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_EventData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CalendarEventType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CalendarEventData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Month = month,
			m_Time = time,
			m_RandomSeed = RandomSeed.Next(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CalendarEventQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.CalendarEventLaunchSystem+CheckEventLaunchJob`  
- `Game.Simulation.CalendarEventLaunchSystem+TypeHandle`  

