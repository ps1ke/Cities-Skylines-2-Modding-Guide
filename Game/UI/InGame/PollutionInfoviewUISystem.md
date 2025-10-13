# Game.UI.InGame.PollutionInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PollutionInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    protected Game.Simulation.CitySystem m_CitySystem;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageGroundPollution;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageWaterPollution;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageAirPollution;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageNoisePollution;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_374463591_0;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    protected System.Boolean Active { protected get; }

    public PollutionInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
}
```


## Fields

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `protected Game.Simulation.CitySystem m_CitySystem`  

```csharp
protected Game.Simulation.CitySystem m_CitySystem;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageGroundPollution`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageGroundPollution;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageWaterPollution`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageWaterPollution;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageAirPollution`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageAirPollution;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageNoisePollution`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageNoisePollution;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_374463591_0`  

```csharp
private Unity.Entities.EntityQuery __query_374463591_0;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public PollutionInfoviewUISystem()`  

```csharp
[Preserve]
	public PollutionInfoviewUISystem()
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
		__query_374463591_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_Results = new NativeArray<int>(8, Allocator.Persistent);
		m_HouseholdQuery = GetEntityQuery(ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<PropertySeeker>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<MovingAway>());
		AddBinding(m_AverageGroundPollution = new ValueBinding<IndicatorValue>("pollutionInfo", "averageGroundPollution", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		AddBinding(m_AverageWaterPollution = new ValueBinding<IndicatorValue>("pollutionInfo", "averageWaterPollution", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		AddBinding(m_AverageAirPollution = new ValueBinding<IndicatorValue>("pollutionInfo", "averageAirPollution", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		AddBinding(m_AverageNoisePollution = new ValueBinding<IndicatorValue>("pollutionInfo", "averageNoisePollution", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		RequireForUpdate<CitizenHappinessParameterData>();
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
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		JobHandle dependencies;
		NativeArray<GroundPollution> map = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies);
		JobHandle dependencies2;
		NativeArray<AirPollution> map2 = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies2);
		JobHandle dependencies3;
		NativeArray<NoisePollution> map3 = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies3);
		JobHandle job = JobHandle.CombineDependencies(dependencies, dependencies2, dependencies3);
		CitizenHappinessParameterData singleton = __query_374463591_0.GetSingleton<CitizenHappinessParameterData>();
		ResetResults();
		JobChunkExtensions.Schedule(new CalculateAveragePollutionJob
		{
			m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterConsumerFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_AirPollutionMap = map2,
			m_NoisePollutionMap = map3,
			m_GroundPollutionMap = map,
			m_HappinessParameters = singleton,
			m_City = m_CitySystem.City,
			m_Results = m_Results
		}, m_HouseholdQuery, JobHandle.CombineDependencies(job, base.Dependency)).Complete();
		int num = m_Results[0];
		int num2 = m_Results[4];
		int num3 = m_Results[2];
		int num4 = m_Results[1];
		int num5 = m_Results[5];
		int num6 = m_Results[3];
		int num7 = m_Results[6];
		int num8 = m_Results[7];
		int num9 = ((num4 > 0) ? (num / num4) : 0);
		int num10 = ((num6 > 0) ? (num3 / num6) : 0);
		int num11 = ((num5 > 0) ? (num2 / num5) : 0);
		m_AverageGroundPollution.Update(new IndicatorValue(0f, singleton.m_MaxAirAndGroundPollutionBonus, -num9));
		m_AverageAirPollution.Update(new IndicatorValue(0f, singleton.m_MaxAirAndGroundPollutionBonus, -num10));
		m_AverageNoisePollution.Update(new IndicatorValue(0f, singleton.m_MaxNoisePollutionBonus, -num11));
		m_AverageWaterPollution.Update(new IndicatorValue(0f, num7, num8));
	}
```

- `private ResetResults() : System.Void`  

```csharp
private void ResetResults()
	{
		for (int i = 0; i < m_Results.Length; i++)
		{
			m_Results[i] = 0;
		}
	}
```


## Nested types

- `Game.UI.InGame.PollutionInfoviewUISystem+Result`  
- `Game.UI.InGame.PollutionInfoviewUISystem+CalculateAveragePollutionJob`  
- `Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle`  

