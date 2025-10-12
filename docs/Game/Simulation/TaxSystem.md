# Game.Simulation.TaxSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ITaxSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Collections.NativeArray<System.Int32> m_TaxRates`  
- `private Unity.Entities.EntityQuery m_ResidentialTaxPayerGroup`  
- `private Unity.Entities.EntityQuery m_CommercialTaxPayerGroup`  
- `private Unity.Entities.EntityQuery m_IndustrialTaxPayerGroup`  
- `private Unity.Entities.EntityQuery m_TaxParameterGroup`  
- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Prefabs.TaxParameterData m_TaxParameterData`  
- `private Unity.Mathematics.float3 m_TaxPaidMultiplier`  
- `private Unity.Jobs.JobHandle m_Readers`  
- `private Game.Simulation.TaxSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public System.Int32 TaxRate { get; set }`  
- `public Unity.Jobs.JobHandle Readers { get }`  

## Constructors

- `public TaxSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  
- `private ClampResidentialTaxRates() : System.Void`  
- `private ClampResourceTaxRates(Game.Simulation.TaxAreaType areaType) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private EnsureAreaTaxRateLimits(Game.Simulation.TaxAreaType areaType) : System.Void`  
- `private EnsureJobLevelTaxRateLimits(System.Int32 jobLevel) : System.Void`  
- `private EnsureResourceTaxRateLimits(Game.Simulation.TaxAreaType areaType, Game.Economy.Resource resource) : System.Void`  
- `private EnsureTaxParameterData() : System.Void`  
- `public GetCommercialTaxRate(Game.Economy.Resource resource) : System.Int32`  
- `public static GetCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public static GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public static GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public static GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public static GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public static GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public GetIndustrialTaxRate(Game.Economy.Resource resource) : System.Int32`  
- `public static GetIndustrialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `private GetJobLevelTaxRateRange() : Unity.Mathematics.int2`  
- `public GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  
- `public static GetModifiedCommercialTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  
- `public GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  
- `public static GetModifiedTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Entities.Entity district, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> policies) : System.Int32`  
- `public GetOfficeTaxRate(Game.Economy.Resource resource) : System.Int32`  
- `public static GetOfficeTaxRate(Game.Economy.Resource resource, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public GetResidentialTaxRate(System.Int32 jobLevel) : System.Int32`  
- `public static GetResidentialTaxRate(System.Int32 jobLevel, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `private GetResourceTaxRateRange(Game.Simulation.TaxAreaType areaType) : Unity.Mathematics.int2`  
- `public static GetTax(Game.Agents.TaxPayer payer) : System.Int32`  
- `public GetTaxParameterData() : Game.Prefabs.TaxParameterData`  
- `public GetTaxRate(Game.Simulation.TaxAreaType areaType) : System.Int32`  
- `public static GetTaxRate(Game.Simulation.TaxAreaType areaType, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate) : System.Int32`  
- `public GetTaxRateRange(Game.Simulation.TaxAreaType areaType) : Unity.Mathematics.int2`  
- `public GetTaxRates() : Unity.Collections.NativeArray<System.Int32>`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `private GetZeroOffset(Game.Simulation.TaxAreaType areaType) : System.Int32`  
- `private static MatchesResultType(System.Int32 amount, Game.Simulation.TaxResultType resultType) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  
- `public SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  
- `public SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate) : System.Void`  
- `public SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate) : System.Void`  

## Nested types

- `Game.Simulation.TaxSystem+PayTaxJob`  
- `Game.Simulation.TaxSystem+TypeHandle`  

