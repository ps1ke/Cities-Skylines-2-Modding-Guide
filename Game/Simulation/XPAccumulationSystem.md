# Game.Simulation.XPAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class XPAccumulationSystem : Game.GameSystemBase
{
    private Game.Simulation.XPSystem m_XPSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_XPSettingsQuery;
    private Game.Simulation.XPAccumulationSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public XPAccumulationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.XPSystem m_XPSystem`  

```csharp
private Game.Simulation.XPSystem m_XPSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_XPSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_XPSettingsQuery;
```

- `private Game.Simulation.XPAccumulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.XPAccumulationSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public XPAccumulationSystem()`  

```csharp
[Preserve]
	public XPAccumulationSystem()
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
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_XPSystem = base.World.GetOrCreateSystemManaged<XPSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_XPSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<XPParameterData>());
		RequireForUpdate(m_XPSettingsQuery);
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
		JobHandle deps;
		XPAccumulateJob jobData = new XPAccumulateJob
		{
			m_CityPopulations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityXPs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_XP_RW_ComponentLookup, ref base.CheckedStateRef),
			m_XPParameters = m_XPSettingsQuery.GetSingleton<XPParameterData>(),
			m_CityStatistics = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RO_BufferLookup, ref base.CheckedStateRef),
			m_StatsLookup = m_CityStatisticsSystem.GetLookup(),
			m_City = m_CitySystem.City,
			m_XPQueue = m_XPSystem.GetQueue(out deps)
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, deps));
		m_XPSystem.AddQueueWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.XPAccumulationSystem+XPAccumulateJob`  
- `Game.Simulation.XPAccumulationSystem+TypeHandle`  

