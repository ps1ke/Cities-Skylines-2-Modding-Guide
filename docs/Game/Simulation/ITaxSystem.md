# Game.Simulation.ITaxSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Properties

- `public System.Int32 TaxRate { get; set }`  
- `public Unity.Jobs.JobHandle Readers { get }`  

## Methods

- `public abstract GetCommercialTaxRate(Game.Economy.Resource resource) : System.Int32`  
- `public abstract GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public abstract GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public abstract GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public abstract GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public abstract GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  
- `public abstract GetIndustrialTaxRate(Game.Economy.Resource resource) : System.Int32`  
- `public abstract GetOfficeTaxRate(Game.Economy.Resource resource) : System.Int32`  
- `public abstract GetResidentialTaxRate(System.Int32 jobLevel) : System.Int32`  
- `public abstract GetTaxParameterData() : Game.Prefabs.TaxParameterData`  
- `public abstract GetTaxRate(Game.Simulation.TaxAreaType areaType) : System.Int32`  
- `public abstract GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate) : System.Int32`  
- `public abstract GetTaxRateRange(Game.Simulation.TaxAreaType areaType) : Unity.Mathematics.int2`  
- `public abstract SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  
- `public abstract SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  
- `public abstract SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  
- `public abstract SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate) : System.Void`  
- `public abstract SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate) : System.Void`  

