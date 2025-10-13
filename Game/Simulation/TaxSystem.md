# Game.Simulation.TaxSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ITaxSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TaxSystem : Game.GameSystemBase, Game.Simulation.ITaxSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Unity.Collections.NativeArray<System.Int32> m_TaxRates;
    private Unity.Entities.EntityQuery m_ResidentialTaxPayerGroup;
    private Unity.Entities.EntityQuery m_CommercialTaxPayerGroup;
    private Unity.Entities.EntityQuery m_IndustrialTaxPayerGroup;
    private Unity.Entities.EntityQuery m_TaxParameterGroup;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.TaxParameterData m_TaxParameterData;
    private Unity.Mathematics.float3 m_TaxPaidMultiplier;
    private Unity.Jobs.JobHandle m_Readers;
    private Game.Simulation.TaxSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public System.Int32 TaxRate { get; set; }
    public Unity.Jobs.JobHandle Readers { get; }

    public TaxSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    private System.Void ClampResidentialTaxRates();
    private System.Void ClampResourceTaxRates(Game.Simulation.TaxAreaType areaType);
    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void EnsureAreaTaxRateLimits(Game.Simulation.TaxAreaType areaType);
    private System.Void EnsureJobLevelTaxRateLimits(System.Int32 jobLevel);
    private System.Void EnsureResourceTaxRateLimits(Game.Simulation.TaxAreaType areaType, Game.Economy.Resource resource);
    private System.Void EnsureTaxParameterData();
    public System.Int32 GetCommercialTaxRate(Game.Economy.Resource resource);
    public static System.Int32 GetCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates);
    public System.Int32 GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public static System.Int32 GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
    public System.Int32 GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public static System.Int32 GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
    public System.Int32 GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public static System.Int32 GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
    public System.Int32 GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public static System.Int32 GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
    public System.Int32 GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public static System.Int32 GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
    public System.Int32 GetIndustrialTaxRate(Game.Economy.Resource resource);
    public static System.Int32 GetIndustrialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates);
    private Unity.Mathematics.int2 GetJobLevelTaxRateRange();
    public System.Int32 GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies);
    public static System.Int32 GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies);
    public System.Int32 GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies);
    public static System.Int32 GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies);
    public System.Int32 GetOfficeTaxRate(Game.Economy.Resource resource);
    public static System.Int32 GetOfficeTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates);
    public System.Int32 GetResidentialTaxRate(System.Int32 jobLevel);
    public static System.Int32 GetResidentialTaxRate(System.Int32 jobLevel, Unity.Collections.NativeArray<System.Int32> taxRates);
    private Unity.Mathematics.int2 GetResourceTaxRateRange(Game.Simulation.TaxAreaType areaType);
    public static System.Int32 GetTax(Game.Agents.TaxPayer payer);
    public Game.Prefabs.TaxParameterData GetTaxParameterData();
    public System.Int32 GetTaxRate(Game.Simulation.TaxAreaType areaType);
    public static System.Int32 GetTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates);
    public System.Int32 GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate);
    public Unity.Mathematics.int2 GetTaxRateRange(Game.Simulation.TaxAreaType areaType);
    public Unity.Collections.NativeArray<System.Int32> GetTaxRates();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    private System.Int32 GetZeroOffset(Game.Simulation.TaxAreaType areaType);
    private static System.Boolean MatchesResultType(System.Int32 amount, Game.Simulation.TaxResultType resultType);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Void SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate);
    public System.Void SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate);
    public System.Void SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate);
    public System.Void SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate);
}
```


## Fields

- `private Unity.Collections.NativeArray<System.Int32> m_TaxRates`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TaxRates;
```

- `private Unity.Entities.EntityQuery m_ResidentialTaxPayerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ResidentialTaxPayerGroup;
```

- `private Unity.Entities.EntityQuery m_CommercialTaxPayerGroup`  

```csharp
private Unity.Entities.EntityQuery m_CommercialTaxPayerGroup;
```

- `private Unity.Entities.EntityQuery m_IndustrialTaxPayerGroup`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialTaxPayerGroup;
```

- `private Unity.Entities.EntityQuery m_TaxParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_TaxParameterGroup;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.TaxParameterData m_TaxParameterData`  

```csharp
private Game.Prefabs.TaxParameterData m_TaxParameterData;
```

- `private Unity.Mathematics.float3 m_TaxPaidMultiplier`  

```csharp
private Unity.Mathematics.float3 m_TaxPaidMultiplier;
```

- `private Unity.Jobs.JobHandle m_Readers`  

```csharp
private Unity.Jobs.JobHandle m_Readers;
```

- `private Game.Simulation.TaxSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TaxSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public System.Int32 TaxRate { get; set }`  

```csharp
public System.Int32 TaxRate { get; set; }
```

- `public Unity.Jobs.JobHandle Readers { get }`  

```csharp
public Unity.Jobs.JobHandle Readers { get; }
```


## Constructors

- `public TaxSystem()`  

```csharp
[Preserve]
	public TaxSystem()
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

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public void AddReader(JobHandle reader)
	{
		m_Readers = JobHandle.CombineDependencies(m_Readers, reader);
	}
```

- `private ClampResidentialTaxRates() : System.Void`  

```csharp
private void ClampResidentialTaxRates()
	{
		int2 jobLevelTaxRateRange = GetJobLevelTaxRateRange();
		int num = 0;
		if (jobLevelTaxRateRange.x > 0)
		{
			num = jobLevelTaxRateRange.x;
		}
		else if (jobLevelTaxRateRange.y < 0)
		{
			num = jobLevelTaxRateRange.y;
		}
		if (num != 0)
		{
			m_TaxRates[1] += num;
			for (int i = 0; i < 5; i++)
			{
				m_TaxRates[5 + i] -= num;
			}
		}
	}
```

- `private ClampResourceTaxRates(Game.Simulation.TaxAreaType areaType) : System.Void`  

```csharp
private void ClampResourceTaxRates(TaxAreaType areaType)
	{
		int2 resourceTaxRateRange = GetResourceTaxRateRange(areaType);
		int num = 0;
		if (resourceTaxRateRange.x > 0)
		{
			num = resourceTaxRateRange.x;
		}
		else if (resourceTaxRateRange.y < 0)
		{
			num = resourceTaxRateRange.y;
		}
		if (num == 0)
		{
			return;
		}
		m_TaxRates[(int)areaType] += num;
		int zeroOffset = GetZeroOffset(areaType);
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		ResourceIterator iterator = ResourceIterator.GetIterator();
		while (iterator.Next())
		{
			Entity entity = prefabs[iterator.resource];
			if (base.EntityManager.TryGetComponent<TaxableResourceData>(entity, out var component) && component.Contains(areaType))
			{
				m_TaxRates[zeroOffset + EconomyUtils.GetResourceIndex(iterator.resource)] -= num;
			}
		}
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private EnsureAreaTaxRateLimits(Game.Simulation.TaxAreaType areaType) : System.Void`  

```csharp
private void EnsureAreaTaxRateLimits(TaxAreaType areaType)
	{
		switch (areaType)
		{
		case TaxAreaType.Residential:
		{
			int2 officeTaxLimits = m_TaxParameterData.m_ResidentialTaxLimits;
			m_TaxRates[(int)areaType] = math.min(officeTaxLimits.y, math.max(officeTaxLimits.x, GetTaxRate(areaType))) - m_TaxRates[0];
			for (int i = 0; i < 5; i++)
			{
				EnsureJobLevelTaxRateLimits(i);
			}
			break;
		}
		case TaxAreaType.Commercial:
		{
			int2 officeTaxLimits = m_TaxParameterData.m_CommercialTaxLimits;
			m_TaxRates[(int)areaType] = math.min(officeTaxLimits.y, math.max(officeTaxLimits.x, GetTaxRate(areaType))) - m_TaxRates[0];
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				if (EconomyUtils.IsCommercialResource(iterator.resource))
				{
					EnsureResourceTaxRateLimits(areaType, iterator.resource);
				}
			}
			break;
		}
		case TaxAreaType.Industrial:
		{
			int2 officeTaxLimits = m_TaxParameterData.m_IndustrialTaxLimits;
			m_TaxRates[(int)areaType] = math.min(officeTaxLimits.y, math.max(officeTaxLimits.x, GetTaxRate(areaType))) - m_TaxRates[0];
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				if (!base.EntityManager.TryGetComponent<ResourceData>(m_ResourceSystem.GetPrefab(iterator.resource), out var component) || (component.m_IsProduceable && component.m_Weight > 0f))
				{
					EnsureResourceTaxRateLimits(areaType, iterator.resource);
				}
			}
			break;
		}
		case TaxAreaType.Office:
		{
			int2 officeTaxLimits = m_TaxParameterData.m_OfficeTaxLimits;
			m_TaxRates[(int)areaType] = math.min(officeTaxLimits.y, math.max(officeTaxLimits.x, GetTaxRate(areaType))) - m_TaxRates[0];
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				if (EconomyUtils.IsOfficeResource(iterator.resource))
				{
					EnsureResourceTaxRateLimits(areaType, iterator.resource);
				}
			}
			break;
		}
		}
	}
```

- `private EnsureJobLevelTaxRateLimits(System.Int32 jobLevel) : System.Void`  

```csharp
private void EnsureJobLevelTaxRateLimits(int jobLevel)
	{
		m_TaxRates[5 + jobLevel] = math.min(m_TaxParameterData.m_JobLevelTaxLimits.y, math.max(m_TaxParameterData.m_JobLevelTaxLimits.x, GetResidentialTaxRate(jobLevel))) - GetTaxRate(TaxAreaType.Residential);
	}
```

- `private EnsureResourceTaxRateLimits(Game.Simulation.TaxAreaType areaType, Game.Economy.Resource resource) : System.Void`  

```csharp
private void EnsureResourceTaxRateLimits(TaxAreaType areaType, Resource resource)
	{
		switch (areaType)
		{
		case TaxAreaType.Commercial:
		{
			int taxRate = GetTaxRate(TaxAreaType.Commercial);
			m_TaxRates[10 + EconomyUtils.GetResourceIndex(resource)] = math.min(m_TaxParameterData.m_ResourceTaxLimits.y, math.max(m_TaxParameterData.m_ResourceTaxLimits.x, GetCommercialTaxRate(resource))) - taxRate;
			break;
		}
		case TaxAreaType.Industrial:
		{
			int taxRate = GetTaxRate(TaxAreaType.Industrial);
			m_TaxRates[51 + EconomyUtils.GetResourceIndex(resource)] = math.min(m_TaxParameterData.m_ResourceTaxLimits.y, math.max(m_TaxParameterData.m_ResourceTaxLimits.x, GetIndustrialTaxRate(resource))) - taxRate;
			break;
		}
		case TaxAreaType.Office:
		{
			int taxRate = GetTaxRate(TaxAreaType.Office);
			m_TaxRates[51 + EconomyUtils.GetResourceIndex(resource)] = math.min(m_TaxParameterData.m_ResourceTaxLimits.y, math.max(m_TaxParameterData.m_ResourceTaxLimits.x, GetOfficeTaxRate(resource))) - taxRate;
			break;
		}
		}
	}
```

- `private EnsureTaxParameterData() : System.Void`  

```csharp
private void EnsureTaxParameterData()
	{
		if (m_TaxParameterData.m_TotalTaxLimits.x == m_TaxParameterData.m_TotalTaxLimits.y)
		{
			m_TaxParameterData = m_TaxParameterGroup.GetSingleton<TaxParameterData>();
		}
	}
```

- `public GetCommercialTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public static int GetCommercialTaxRate(Resource resource, NativeArray<int> taxRates)
	{
		return GetTaxRate(TaxAreaType.Commercial, taxRates) + taxRates[10 + EconomyUtils.GetResourceIndex(resource)];
	}
```

- `public static GetCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetCommercialTaxRate(Resource resource, NativeArray<int> taxRates)
	{
		return GetTaxRate(TaxAreaType.Commercial, taxRates) + taxRates[10 + EconomyUtils.GetResourceIndex(resource)];
	}
```

- `public GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public static int GetEstimatedCommercialTaxIncome(Resource resource, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		return (int)((long)GetCommercialTaxRate(resource, taxRates) * (long)CityStatisticsSystem.GetStatisticValue(statisticsLookup, stats, StatisticType.CommercialTaxableIncome, EconomyUtils.GetResourceIndex(resource)) / 100);
	}
```

- `public static GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetEstimatedCommercialTaxIncome(Resource resource, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		return (int)((long)GetCommercialTaxRate(resource, taxRates) * (long)CityStatisticsSystem.GetStatisticValue(statisticsLookup, stats, StatisticType.CommercialTaxableIncome, EconomyUtils.GetResourceIndex(resource)) / 100);
	}
```

- `public GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public static int GetEstimatedIndustrialTaxIncome(Resource resource, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		return (int)((long)GetIndustrialTaxRate(resource, taxRates) * (long)CityStatisticsSystem.GetStatisticValue(statisticsLookup, stats, StatisticType.IndustrialTaxableIncome, EconomyUtils.GetResourceIndex(resource)) / 100);
	}
```

- `public static GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetEstimatedIndustrialTaxIncome(Resource resource, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		return (int)((long)GetIndustrialTaxRate(resource, taxRates) * (long)CityStatisticsSystem.GetStatisticValue(statisticsLookup, stats, StatisticType.IndustrialTaxableIncome, EconomyUtils.GetResourceIndex(resource)) / 100);
	}
```

- `public GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public static int GetEstimatedOfficeTaxIncome(Resource resource, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		return (int)((long)GetOfficeTaxRate(resource, taxRates) * (long)CityStatisticsSystem.GetStatisticValue(statisticsLookup, stats, StatisticType.OfficeTaxableIncome, EconomyUtils.GetResourceIndex(resource)) / 100);
	}
```

- `public static GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetEstimatedOfficeTaxIncome(Resource resource, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		return (int)((long)GetOfficeTaxRate(resource, taxRates) * (long)CityStatisticsSystem.GetStatisticValue(statisticsLookup, stats, StatisticType.OfficeTaxableIncome, EconomyUtils.GetResourceIndex(resource)) / 100);
	}
```

- `public GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public static int GetEstimatedResidentialTaxIncome(int jobLevel, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		return (int)((long)GetResidentialTaxRate(jobLevel, taxRates) * (long)CityStatisticsSystem.GetStatisticValue(statisticsLookup, stats, StatisticType.ResidentialTaxableIncome, jobLevel) / 100);
	}
```

- `public static GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetEstimatedResidentialTaxIncome(int jobLevel, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		return (int)((long)GetResidentialTaxRate(jobLevel, taxRates) * (long)CityStatisticsSystem.GetStatisticValue(statisticsLookup, stats, StatisticType.ResidentialTaxableIncome, jobLevel) / 100);
	}
```

- `public GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public static int GetEstimatedTaxAmount(TaxAreaType areaType, TaxResultType resultType, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		int num = 0;
		switch (areaType)
		{
		case TaxAreaType.Residential:
		{
			for (int i = 0; i < 5; i++)
			{
				int estimatedResidentialTaxIncome = GetEstimatedResidentialTaxIncome(i, statisticsLookup, stats, taxRates);
				if (MatchesResultType(estimatedResidentialTaxIncome, resultType))
				{
					num += estimatedResidentialTaxIncome;
				}
			}
			return num;
		}
		case TaxAreaType.Commercial:
		{
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				int estimatedCommercialTaxIncome = GetEstimatedCommercialTaxIncome(iterator.resource, statisticsLookup, stats, taxRates);
				if (MatchesResultType(estimatedCommercialTaxIncome, resultType))
				{
					num += estimatedCommercialTaxIncome;
				}
			}
			return num;
		}
		case TaxAreaType.Industrial:
		{
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				int estimatedIndustrialTaxIncome = GetEstimatedIndustrialTaxIncome(iterator.resource, statisticsLookup, stats, taxRates);
				if (MatchesResultType(estimatedIndustrialTaxIncome, resultType))
				{
					num += estimatedIndustrialTaxIncome;
				}
			}
			return num;
		}
		case TaxAreaType.Office:
		{
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				int estimatedOfficeTaxIncome = GetEstimatedOfficeTaxIncome(iterator.resource, statisticsLookup, stats, taxRates);
				if (MatchesResultType(estimatedOfficeTaxIncome, resultType))
				{
					num += estimatedOfficeTaxIncome;
				}
			}
			return num;
		}
		default:
			return 0;
		}
	}
```

- `public static GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetEstimatedTaxAmount(TaxAreaType areaType, TaxResultType resultType, NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> statisticsLookup, BufferLookup<CityStatistic> stats, NativeArray<int> taxRates)
	{
		int num = 0;
		switch (areaType)
		{
		case TaxAreaType.Residential:
		{
			for (int i = 0; i < 5; i++)
			{
				int estimatedResidentialTaxIncome = GetEstimatedResidentialTaxIncome(i, statisticsLookup, stats, taxRates);
				if (MatchesResultType(estimatedResidentialTaxIncome, resultType))
				{
					num += estimatedResidentialTaxIncome;
				}
			}
			return num;
		}
		case TaxAreaType.Commercial:
		{
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				int estimatedCommercialTaxIncome = GetEstimatedCommercialTaxIncome(iterator.resource, statisticsLookup, stats, taxRates);
				if (MatchesResultType(estimatedCommercialTaxIncome, resultType))
				{
					num += estimatedCommercialTaxIncome;
				}
			}
			return num;
		}
		case TaxAreaType.Industrial:
		{
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				int estimatedIndustrialTaxIncome = GetEstimatedIndustrialTaxIncome(iterator.resource, statisticsLookup, stats, taxRates);
				if (MatchesResultType(estimatedIndustrialTaxIncome, resultType))
				{
					num += estimatedIndustrialTaxIncome;
				}
			}
			return num;
		}
		case TaxAreaType.Office:
		{
			ResourceIterator iterator = ResourceIterator.GetIterator();
			while (iterator.Next())
			{
				int estimatedOfficeTaxIncome = GetEstimatedOfficeTaxIncome(iterator.resource, statisticsLookup, stats, taxRates);
				if (MatchesResultType(estimatedOfficeTaxIncome, resultType))
				{
					num += estimatedOfficeTaxIncome;
				}
			}
			return num;
		}
		default:
			return 0;
		}
	}
```

- `public GetIndustrialTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public static int GetIndustrialTaxRate(Resource resource, NativeArray<int> taxRates)
	{
		return GetTaxRate(TaxAreaType.Industrial, taxRates) + taxRates[51 + EconomyUtils.GetResourceIndex(resource)];
	}
```

- `public static GetIndustrialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetIndustrialTaxRate(Resource resource, NativeArray<int> taxRates)
	{
		return GetTaxRate(TaxAreaType.Industrial, taxRates) + taxRates[51 + EconomyUtils.GetResourceIndex(resource)];
	}
```

- `private GetJobLevelTaxRateRange() : Unity.Mathematics.int2`  

```csharp
private int2 GetJobLevelTaxRateRange()
	{
		int2 result = new int2(int.MaxValue, int.MinValue);
		for (int i = 0; i < 5; i++)
		{
			int y = m_TaxRates[5 + i];
			result.x = math.min(result.x, y);
			result.y = math.max(result.y, y);
		}
		return result;
	}
```

- `public GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  

```csharp
public static int GetModifiedCommercialTaxRate(Resource resource, NativeArray<int> taxRates, Entity district, BufferLookup<DistrictModifier> policies)
	{
		return GetModifiedTaxRate(TaxAreaType.Commercial, taxRates, district, policies) + taxRates[10 + EconomyUtils.GetResourceIndex(resource)];
	}
```

- `public static GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  

```csharp
public static int GetModifiedCommercialTaxRate(Resource resource, NativeArray<int> taxRates, Entity district, BufferLookup<DistrictModifier> policies)
	{
		return GetModifiedTaxRate(TaxAreaType.Commercial, taxRates, district, policies) + taxRates[10 + EconomyUtils.GetResourceIndex(resource)];
	}
```

- `public GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  

```csharp
public static int GetModifiedTaxRate(TaxAreaType areaType, NativeArray<int> taxRates, Entity district, BufferLookup<DistrictModifier> policies)
	{
		float value = GetTaxRate(areaType, taxRates);
		if (policies.HasBuffer(district))
		{
			DynamicBuffer<DistrictModifier> modifiers = policies[district];
			AreaUtils.ApplyModifier(ref value, modifiers, DistrictModifierType.LowCommercialTax);
		}
		return (int)math.round(value);
	}
```

- `public static GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  

```csharp
public static int GetModifiedTaxRate(TaxAreaType areaType, NativeArray<int> taxRates, Entity district, BufferLookup<DistrictModifier> policies)
	{
		float value = GetTaxRate(areaType, taxRates);
		if (policies.HasBuffer(district))
		{
			DynamicBuffer<DistrictModifier> modifiers = policies[district];
			AreaUtils.ApplyModifier(ref value, modifiers, DistrictModifierType.LowCommercialTax);
		}
		return (int)math.round(value);
	}
```

- `public GetOfficeTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public static int GetOfficeTaxRate(Resource resource, NativeArray<int> taxRates)
	{
		return GetTaxRate(TaxAreaType.Office, taxRates) + taxRates[51 + EconomyUtils.GetResourceIndex(resource)];
	}
```

- `public static GetOfficeTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetOfficeTaxRate(Resource resource, NativeArray<int> taxRates)
	{
		return GetTaxRate(TaxAreaType.Office, taxRates) + taxRates[51 + EconomyUtils.GetResourceIndex(resource)];
	}
```

- `public GetResidentialTaxRate(System.Int32 jobLevel) : System.Int32`  

```csharp
public static int GetResidentialTaxRate(int jobLevel, NativeArray<int> taxRates)
	{
		return GetTaxRate(TaxAreaType.Residential, taxRates) + taxRates[5 + jobLevel];
	}
```

- `public static GetResidentialTaxRate(System.Int32 jobLevel, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetResidentialTaxRate(int jobLevel, NativeArray<int> taxRates)
	{
		return GetTaxRate(TaxAreaType.Residential, taxRates) + taxRates[5 + jobLevel];
	}
```

- `private GetResourceTaxRateRange(Game.Simulation.TaxAreaType areaType) : Unity.Mathematics.int2`  

```csharp
private int2 GetResourceTaxRateRange(TaxAreaType areaType)
	{
		int2 result = new int2(int.MaxValue, int.MinValue);
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		ResourceIterator iterator = ResourceIterator.GetIterator();
		int zeroOffset = GetZeroOffset(areaType);
		while (iterator.Next())
		{
			Entity entity = prefabs[iterator.resource];
			if (base.EntityManager.TryGetComponent<TaxableResourceData>(entity, out var component) && component.Contains(areaType))
			{
				int y = m_TaxRates[zeroOffset + EconomyUtils.GetResourceIndex(iterator.resource)];
				result.x = math.min(result.x, y);
				result.y = math.max(result.y, y);
			}
		}
		return result;
	}
```

- `public static GetTax(Game.Agents.TaxPayer payer) : System.Int32`  

```csharp
public static int GetTax(TaxPayer payer)
	{
		return (int)math.round(0.01f * (float)payer.m_AverageTaxRate * (float)payer.m_UntaxedIncome);
	}
```

- `public GetTaxParameterData() : Game.Prefabs.TaxParameterData`  

```csharp
public TaxParameterData GetTaxParameterData()
	{
		if (!m_TaxParameterGroup.IsEmptyIgnoreFilter)
		{
			EnsureTaxParameterData();
			return m_TaxParameterData;
		}
		return default(TaxParameterData);
	}
```

- `public GetTaxRate(Game.Simulation.TaxAreaType areaType) : System.Int32`  

```csharp
public static int GetTaxRate(TaxAreaType areaType, NativeArray<int> taxRates)
	{
		return taxRates[0] + taxRates[(int)areaType];
	}
```

- `public static GetTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetTaxRate(TaxAreaType areaType, NativeArray<int> taxRates)
	{
		return taxRates[0] + taxRates[(int)areaType];
	}
```

- `public GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate) : System.Int32`  

```csharp
public int GetTaxRateEffect(TaxAreaType areaType, int taxRate)
	{
		return 0;
	}
```

- `public GetTaxRateRange(Game.Simulation.TaxAreaType areaType) : Unity.Mathematics.int2`  

```csharp
public int2 GetTaxRateRange(TaxAreaType areaType)
	{
		if (areaType == TaxAreaType.Residential)
		{
			return GetTaxRate(areaType) + GetJobLevelTaxRateRange();
		}
		return GetTaxRate(areaType) + GetResourceTaxRateRange(areaType);
	}
```

- `public GetTaxRates() : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetTaxRates()
	{
		return m_TaxRates;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `private GetZeroOffset(Game.Simulation.TaxAreaType areaType) : System.Int32`  

```csharp
private int GetZeroOffset(TaxAreaType areaType)
	{
		switch (areaType)
		{
		case TaxAreaType.Commercial:
			return 10;
		case TaxAreaType.Industrial:
		case TaxAreaType.Office:
			return 51;
		default:
			throw new ArgumentOutOfRangeException("areaType", areaType, null);
		}
	}
```

- `private static MatchesResultType(System.Int32 amount, Game.Simulation.TaxResultType resultType) : System.Boolean`  

```csharp
private static bool MatchesResultType(int amount, TaxResultType resultType)
	{
		if (resultType != TaxResultType.Any && (resultType != TaxResultType.Income || amount <= 0))
		{
			if (resultType == TaxResultType.Expense)
			{
				return amount < 0;
			}
			return false;
		}
		return true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_ResidentialTaxPayerGroup = GetEntityQuery(ComponentType.ReadWrite<TaxPayer>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<Resources>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.ReadOnly<Household>());
		m_CommercialTaxPayerGroup = GetEntityQuery(ComponentType.ReadWrite<TaxPayer>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<Resources>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.ReadOnly<ServiceAvailable>());
		m_IndustrialTaxPayerGroup = GetEntityQuery(ComponentType.ReadWrite<TaxPayer>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<Resources>(), ComponentType.ReadOnly<Game.Companies.ProcessingCompany>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Game.Companies.StorageCompany>(), ComponentType.Exclude<ServiceAvailable>());
		m_TaxParameterGroup = GetEntityQuery(ComponentType.ReadOnly<TaxParameterData>());
		m_GameModeSettingQuery = GetEntityQuery(ComponentType.ReadOnly<ModeSettingData>());
		m_TaxRates = new NativeArray<int>(92, Allocator.Persistent);
		m_TaxRates[0] = 10;
		m_TaxPaidMultiplier = new float3(1f, 1f, 1f);
		RequireForUpdate(m_TaxParameterGroup);
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
		m_TaxRates.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (m_GameModeSettingQuery.IsEmptyIgnoreFilter)
		{
			m_TaxPaidMultiplier = new float3(1f, 1f, 1f);
			return;
		}
		ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
		if (singleton.m_Enable)
		{
			m_TaxPaidMultiplier = singleton.m_TaxPaidMultiplier;
		}
		else
		{
			m_TaxPaidMultiplier = new float3(1f, 1f, 1f);
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EnsureTaxParameterData();
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		m_TaxParameterData = m_TaxParameterGroup.GetSingleton<TaxParameterData>();
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		JobHandle deps;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new PayTaxJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TaxPayerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_TaxPayer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = GetSharedComponentTypeHandle<UpdateFrame>(),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = prefabs,
			m_Type = IncomeSource.TaxResidential,
			m_UpdateFrameIndex = updateFrame,
			m_PaidMultiplier = m_TaxPaidMultiplier.x,
			m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps).AsParallelWriter()
		}, m_ResidentialTaxPayerGroup, JobHandle.CombineDependencies(base.Dependency, deps));
		m_CityStatisticsSystem.AddWriter(jobHandle);
		updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new PayTaxJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TaxPayerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_TaxPayer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = GetSharedComponentTypeHandle<UpdateFrame>(),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = prefabs,
			m_Type = IncomeSource.TaxCommercial,
			m_UpdateFrameIndex = updateFrame,
			m_PaidMultiplier = m_TaxPaidMultiplier.y,
			m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps).AsParallelWriter()
		}, m_CommercialTaxPayerGroup, JobHandle.CombineDependencies(base.Dependency, deps));
		m_CityStatisticsSystem.AddWriter(jobHandle2);
		JobHandle jobHandle3 = JobChunkExtensions.ScheduleParallel(new PayTaxJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TaxPayerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_TaxPayer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = GetSharedComponentTypeHandle<UpdateFrame>(),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = prefabs,
			m_Type = IncomeSource.TaxIndustrial,
			m_UpdateFrameIndex = updateFrame,
			m_PaidMultiplier = m_TaxPaidMultiplier.z,
			m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps).AsParallelWriter()
		}, m_IndustrialTaxPayerGroup, JobHandle.CombineDependencies(base.Dependency, deps));
		m_CityStatisticsSystem.AddWriter(jobHandle3);
		base.Dependency = JobHandle.CombineDependencies(jobHandle, jobHandle2, jobHandle3);
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (context.version < Version.averageTaxRate)
		{
			m_TaxRates[0] = 10;
			for (int i = 1; i < m_TaxRates.Length; i++)
			{
				m_TaxRates[i] = 0;
			}
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public void SetCommercialTaxRate(Resource resource, int rate)
	{
		m_TaxRates[10 + EconomyUtils.GetResourceIndex(resource)] = rate - GetTaxRate(TaxAreaType.Commercial);
		EnsureResourceTaxRateLimits(TaxAreaType.Commercial, resource);
		ClampResourceTaxRates(TaxAreaType.Commercial);
	}
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_TaxRates[0] = 10;
		for (int i = 1; i < m_TaxRates.Length; i++)
		{
			m_TaxRates[i] = 0;
		}
	}
```

- `public SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public void SetIndustrialTaxRate(Resource resource, int rate)
	{
		m_TaxRates[51 + EconomyUtils.GetResourceIndex(resource)] = rate - GetTaxRate(TaxAreaType.Industrial);
		EnsureResourceTaxRateLimits(TaxAreaType.Industrial, resource);
		ClampResourceTaxRates(TaxAreaType.Industrial);
	}
```

- `public SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public void SetOfficeTaxRate(Resource resource, int rate)
	{
		m_TaxRates[51 + EconomyUtils.GetResourceIndex(resource)] = rate - GetTaxRate(TaxAreaType.Office);
		EnsureResourceTaxRateLimits(TaxAreaType.Office, resource);
		ClampResourceTaxRates(TaxAreaType.Office);
	}
```

- `public SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate) : System.Void`  

```csharp
public void SetResidentialTaxRate(int jobLevel, int rate)
	{
		m_TaxRates[5 + jobLevel] = rate - GetTaxRate(TaxAreaType.Residential);
		EnsureJobLevelTaxRateLimits(jobLevel);
		ClampResidentialTaxRates();
	}
```

- `public SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate) : System.Void`  

```csharp
public void SetTaxRate(TaxAreaType areaType, int rate)
	{
		m_TaxRates[(int)areaType] = rate - m_TaxRates[0];
		EnsureAreaTaxRateLimits(areaType);
	}
```


## Nested types

- `Game.Simulation.TaxSystem+PayTaxJob`  
- `Game.Simulation.TaxSystem+TypeHandle`  

