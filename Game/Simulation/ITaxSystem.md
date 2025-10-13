# Game.Simulation.ITaxSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ITaxSystem
{
    public System.Int32 TaxRate { get; set; }
    public Unity.Jobs.JobHandle Readers { get; }

    public abstract System.Int32 GetCommercialTaxRate(Game.Economy.Resource resource);
    public abstract System.Int32 GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public abstract System.Int32 GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public abstract System.Int32 GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public abstract System.Int32 GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public abstract System.Int32 GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
    public abstract System.Int32 GetIndustrialTaxRate(Game.Economy.Resource resource);
    public abstract System.Int32 GetOfficeTaxRate(Game.Economy.Resource resource);
    public abstract System.Int32 GetResidentialTaxRate(System.Int32 jobLevel);
    public abstract Game.Prefabs.TaxParameterData GetTaxParameterData();
    public abstract System.Int32 GetTaxRate(Game.Simulation.TaxAreaType areaType);
    public abstract System.Int32 GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate);
    public abstract Unity.Mathematics.int2 GetTaxRateRange(Game.Simulation.TaxAreaType areaType);
    public abstract System.Void SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate);
    public abstract System.Void SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate);
    public abstract System.Void SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate);
    public abstract System.Void SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate);
    public abstract System.Void SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate);
}
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


## Methods

- `public abstract GetCommercialTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public abstract System.Int32 GetCommercialTaxRate(Game.Economy.Resource resource);
```

- `public abstract GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public abstract System.Int32 GetEstimatedCommercialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public abstract GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public abstract System.Int32 GetEstimatedIndustrialTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public abstract GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public abstract System.Int32 GetEstimatedOfficeTaxIncome(Game.Economy.Resource resource, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public abstract GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public abstract System.Int32 GetEstimatedResidentialTaxIncome(System.Int32 jobLevel, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public abstract GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats) : System.Int32`  

```csharp
public abstract System.Int32 GetEstimatedTaxAmount(Game.Simulation.TaxAreaType areaType, Game.Simulation.TaxResultType resultType, Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats);
```

- `public abstract GetIndustrialTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public abstract System.Int32 GetIndustrialTaxRate(Game.Economy.Resource resource);
```

- `public abstract GetOfficeTaxRate(Game.Economy.Resource resource) : System.Int32`  

```csharp
public abstract System.Int32 GetOfficeTaxRate(Game.Economy.Resource resource);
```

- `public abstract GetResidentialTaxRate(System.Int32 jobLevel) : System.Int32`  

```csharp
public abstract System.Int32 GetResidentialTaxRate(System.Int32 jobLevel);
```

- `public abstract GetTaxParameterData() : Game.Prefabs.TaxParameterData`  

```csharp
public abstract Game.Prefabs.TaxParameterData GetTaxParameterData();
```

- `public abstract GetTaxRate(Game.Simulation.TaxAreaType areaType) : System.Int32`  

```csharp
public abstract System.Int32 GetTaxRate(Game.Simulation.TaxAreaType areaType);
```

- `public abstract GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate) : System.Int32`  

```csharp
public abstract System.Int32 GetTaxRateEffect(Game.Simulation.TaxAreaType areaType, System.Int32 taxRate);
```

- `public abstract GetTaxRateRange(Game.Simulation.TaxAreaType areaType) : Unity.Mathematics.int2`  

```csharp
public abstract Unity.Mathematics.int2 GetTaxRateRange(Game.Simulation.TaxAreaType areaType);
```

- `public abstract SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public abstract System.Void SetCommercialTaxRate(Game.Economy.Resource resource, System.Int32 rate);
```

- `public abstract SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public abstract System.Void SetIndustrialTaxRate(Game.Economy.Resource resource, System.Int32 rate);
```

- `public abstract SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate) : System.Void`  

```csharp
public abstract System.Void SetOfficeTaxRate(Game.Economy.Resource resource, System.Int32 rate);
```

- `public abstract SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate) : System.Void`  

```csharp
public abstract System.Void SetResidentialTaxRate(System.Int32 jobLevel, System.Int32 rate);
```

- `public abstract SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate) : System.Void`  

```csharp
public abstract System.Void SetTaxRate(Game.Simulation.TaxAreaType areaType, System.Int32 rate);
```


