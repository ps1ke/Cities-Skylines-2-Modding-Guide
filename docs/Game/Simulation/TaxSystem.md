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
public TaxSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public System.Void AddReader(Unity.Jobs.JobHandle reader);
```

- `private ClampResidentialTaxRates() : System.Void`  

```csharp
private System.Void ClampResidentialTaxRates();
```

- `private ClampResourceTaxRates(Game.Simulation.TaxAreaType areaType) : System.Void`  

```csharp
private System.Void ClampResourceTaxRates(Game.Simulation.TaxAreaType areaType);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private EnsureAreaTaxRateLimits(Game.Simulation.TaxAreaType areaType) : System.Void`  

```csharp
private System.Void EnsureAreaTaxRateLimits(Game.Simulation.TaxAreaType areaType);
```

- `private EnsureJobLevelTaxRateLimits(System.Int32 jobLevel) : System.Void`  

```csharp
private System.Void EnsureJobLevelTaxRateLimits(System.Int32 jobLevel);
```

- `private EnsureResourceTaxRateLimits(Game.Simulation.TaxAreaType areaType, Game.Economy.Resource resource) : System.Void`  

```csharp
private System.Void EnsureResourceTaxRateLimits(Game.Simulation.TaxAreaType areaType, Game.Economy.Resource resource);
```

- `private EnsureTaxParameterData() : System.Void`  

```csharp
private System.Void EnsureTaxParameterData();
```

- `public GetCommercialTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public System.Int32 GetCommercialTaxRate(Game.Economy.Resource resource);
```

- `public static GetCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public System.Int32 GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public static GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public System.Int32 GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public static GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public System.Int32 GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public static GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public System.Int32 GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public static GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public System.Int32 GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public static GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public GetIndustrialTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public System.Int32 GetIndustrialTaxRate(Game.Economy.Resource resource);
```

- `public static GetIndustrialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetIndustrialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `private GetJobLevelTaxRateRange() : Unity.Mathematics.int2`  

```csharp
private Unity.Mathematics.int2 GetJobLevelTaxRateRange();
```

- `public GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  

```csharp
public System.Int32 GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies);
```

- `public static GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  

```csharp
public static System.Int32 GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies);
```

- `public GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  

```csharp
public System.Int32 GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies);
```

- `public static GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  

```csharp
public static System.Int32 GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies);
```

- `public GetOfficeTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public System.Int32 GetOfficeTaxRate(Game.Economy.Resource resource);
```

- `public static GetOfficeTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetOfficeTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public GetResidentialTaxRate(System.Int32 jobLevel) : System.Int32`  

```csharp
public System.Int32 GetResidentialTaxRate(System.Int32 jobLevel);
```

- `public static GetResidentialTaxRate(System.Int32 jobLevel, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetResidentialTaxRate(System.Int32 jobLevel, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `private GetResourceTaxRateRange(Game.Simulation.TaxAreaType areaType) : Unity.Mathematics.int2`  

```csharp
private Unity.Mathematics.int2 GetResourceTaxRateRange(Game.Simulation.TaxAreaType areaType);
```

- `public static GetTax(Game.Agents.TaxPayer payer) : System.Int32`  

```csharp
public static System.Int32 GetTax(Game.Agents.TaxPayer payer);
```

- `public GetTaxParameterData() : Game.Prefabs.TaxParameterData`  

```csharp
public Game.Prefabs.TaxParameterData GetTaxParameterData();
```

- `public GetTaxRate(Game.Simulation.TaxAreaType areaType) : System.Int32`  

```csharp
public System.Int32 GetTaxRate(Game.Simulation.TaxAreaType areaType);
```

- `public static GetTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate) : System.Int32`  

```csharp
public System.Int32 GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate);
```

- `public GetTaxRateRange(Game.Simulation.TaxAreaType areaType) : Unity.Mathematics.int2`  

```csharp
public Unity.Mathematics.int2 GetTaxRateRange(Game.Simulation.TaxAreaType areaType);
```

- `public GetTaxRates() : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetTaxRates();
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `private GetZeroOffset(Game.Simulation.TaxAreaType areaType) : System.Int32`  

```csharp
private System.Int32 GetZeroOffset(Game.Simulation.TaxAreaType areaType);
```

- `private static MatchesResultType(System.Int32 amount, Game.Simulation.TaxResultType resultType) : System.Boolean`  

```csharp
private static System.Boolean MatchesResultType(System.Int32 amount, Game.Simulation.TaxResultType resultType);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public System.Void SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `public SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public System.Void SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate);
```

- `public SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public System.Void SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate);
```

- `public SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate) : System.Void`  

```csharp
public System.Void SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate);
```

- `public SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate) : System.Void`  

```csharp
public System.Void SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate);
```


## Nested types

- `Game.Simulation.TaxSystem+PayTaxJob`  
- `Game.Simulation.TaxSystem+TypeHandle`  

