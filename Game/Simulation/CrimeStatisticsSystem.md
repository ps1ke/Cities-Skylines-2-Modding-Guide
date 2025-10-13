# Game.Simulation.CrimeStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CrimeStatisticsSystem : Game.GameSystemBase
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_CrimeProducerQuery;
    private Game.Simulation.CrimeStatisticsSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_263205583_0;

    public CrimeStatisticsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerQuery;
```

- `private Game.Simulation.CrimeStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CrimeStatisticsSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_263205583_0`  

```csharp
private Unity.Entities.EntityQuery __query_263205583_0;
```


## Constructors

- `public CrimeStatisticsSystem()`  

```csharp
[Preserve]
	public CrimeStatisticsSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<PoliceConfigurationData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_263205583_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 8192;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_CrimeProducerQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<CrimeProducer>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_CrimeProducerQuery);
		RequireForUpdate<PoliceConfigurationData>();
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
		PoliceConfigurationData singleton = __query_263205583_0.GetSingleton<PoliceConfigurationData>();
		if (!base.EntityManager.HasEnabledComponent<Locked>(singleton.m_PoliceServicePrefab))
		{
			NativeAccumulator<AverageFloat> averageCrime = new NativeAccumulator<AverageFloat>(Allocator.TempJob);
			AverageCrimeJob jobData = new AverageCrimeJob
			{
				m_CrimeProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MaxCrimeAccumulation = singleton.m_MaxCrimeAccumulation,
				m_AverageCrime = averageCrime.AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CrimeProducerQuery, base.Dependency);
			JobHandle deps;
			StatisticsJob jobData2 = new StatisticsJob
			{
				m_AverageCrime = averageCrime,
				m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps)
			};
			base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, deps));
			m_CityStatisticsSystem.AddWriter(base.Dependency);
			averageCrime.Dispose(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.CrimeStatisticsSystem+AverageCrimeJob`  
- `Game.Simulation.CrimeStatisticsSystem+StatisticsJob`  
- `Game.Simulation.CrimeStatisticsSystem+TypeHandle`  

