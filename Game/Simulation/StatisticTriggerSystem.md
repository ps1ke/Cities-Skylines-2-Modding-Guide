# Game.Simulation.StatisticTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StatisticTriggerSystem : Game.GameSystemBase
{
    private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.StatisticTriggerSystem+TypeHandle __TypeHandle;
    public static const System.Int32 kUpdatesPerDay;

    public StatisticTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.StatisticTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StatisticTriggerSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public StatisticTriggerSystem()`  

```csharp
[Preserve]
	public StatisticTriggerSystem()
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
		return 8192;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 0;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<StatisticTriggerData>(), ComponentType.ReadOnly<TriggerData>());
		RequireForUpdate(m_PrefabQuery);
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
		SendTriggersJob jobData = new SendTriggersJob
		{
			m_EntityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_StatisticTriggerDataHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_StatisticTriggerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StatisticsDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StatisticsData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Locked = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityStatistics = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RO_BufferLookup, ref base.CheckedStateRef),
			m_StatisticsLookup = m_CityStatisticsSystem.GetLookup(),
			m_ActionQueue = m_TriggerSystem.CreateActionBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_PrefabQuery, base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.StatisticTriggerSystem+SendTriggersJob`  
- `Game.Simulation.StatisticTriggerSystem+TypeHandle`  

