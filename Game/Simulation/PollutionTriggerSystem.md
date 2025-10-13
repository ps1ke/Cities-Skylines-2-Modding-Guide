# Game.Simulation.PollutionTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PollutionTriggerSystem : Game.GameSystemBase
{
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private Unity.Collections.NativeArray<System.Single> m_AirPollutionResult;
    private Game.Simulation.PollutionTriggerSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_380796347_0;

    public PollutionTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_AirPollutionResult`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_AirPollutionResult;
```

- `private Game.Simulation.PollutionTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PollutionTriggerSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_380796347_0`  

```csharp
private Unity.Entities.EntityQuery __query_380796347_0;
```


## Constructors

- `public PollutionTriggerSystem()`  

```csharp
[Preserve]
	public PollutionTriggerSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<CitizenHappinessParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_380796347_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 4096;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_HouseholdQuery = GetEntityQuery(ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<MovingAway>());
		m_AirPollutionResult = new NativeArray<float>(1, Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_AirPollutionResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeAccumulator<AverageFloat> result = new NativeAccumulator<AverageFloat>(Allocator.TempJob);
		JobHandle dependencies;
		CalculateAverageAirPollutionJob jobData = new CalculateAverageAirPollutionJob
		{
			m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies),
			m_HappinessParameters = __query_380796347_0.GetSingleton<CitizenHappinessParameterData>(),
			m_City = m_CitySystem.City,
			m_Result = result.AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_HouseholdQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_AirPollutionSystem.AddReader(base.Dependency);
		SendPollutionTriggerJob jobData2 = new SendPollutionTriggerJob
		{
			m_Result = result,
			m_TriggerQueue = m_TriggerSystem.CreateActionBuffer()
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
		result.Dispose(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.PollutionTriggerSystem+CalculateAverageAirPollutionJob`  
- `Game.Simulation.PollutionTriggerSystem+SendPollutionTriggerJob`  
- `Game.Simulation.PollutionTriggerSystem+TypeHandle`  

