# Game.Simulation.ICityStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ICityStatisticsSystem
{
    public System.Action eventStatisticsUpdated { get; set; }
    public System.Int32 sampleCount { get; }

    public abstract System.Void CompleteWriters();
    public abstract Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> GetLookup();
    public abstract System.UInt32 GetSampleFrameIndex(System.Int32 index);
    public abstract Unity.Collections.NativeArray<Game.City.CityStatistic> GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter);
    public abstract Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter);
    public abstract Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public abstract Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter);
    public abstract Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public abstract System.Int32 GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter);
    public abstract System.Int32 GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public abstract System.Int64 GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter);
    public abstract System.Int64 GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
}
```


## Properties

- `public System.Action eventStatisticsUpdated { get; set }`  

```csharp
public System.Action eventStatisticsUpdated { get; set; }
```

- `public System.Int32 sampleCount { get }`  

```csharp
public System.Int32 sampleCount { get; }
```


## Methods

- `public abstract CompleteWriters() : System.Void`  

```csharp
public abstract System.Void CompleteWriters();
```

- `public abstract GetLookup() : Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity>`  

```csharp
public abstract Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> GetLookup();
```

- `public abstract GetSampleFrameIndex(System.Int32 index) : System.UInt32`  

```csharp
public abstract System.UInt32 GetSampleFrameIndex(System.Int32 index);
```

- `public abstract GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<Game.City.CityStatistic>`  

```csharp
public abstract Unity.Collections.NativeArray<Game.City.CityStatistic> GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter);
```

- `public abstract GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public abstract Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter);
```

- `public abstract GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public abstract Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public abstract GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public abstract Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter);
```

- `public abstract GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public abstract Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public abstract GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  

```csharp
public abstract System.Int32 GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter);
```

- `public abstract GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  

```csharp
public abstract System.Int32 GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public abstract GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

```csharp
public abstract System.Int64 GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter);
```

- `public abstract GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

```csharp
public abstract System.Int64 GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```


