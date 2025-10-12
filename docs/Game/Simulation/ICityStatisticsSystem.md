# Game.Simulation.ICityStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** interface abstract public  


## Properties

- `public System.Action eventStatisticsUpdated { get; set }`  
- `public System.Int32 sampleCount { get }`  

## Methods

- `public abstract CompleteWriters() : System.Void`  
- `public abstract GetLookup() : Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity>`  
- `public abstract GetSampleFrameIndex(System.Int32 index) : System.UInt32`  
- `public abstract GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<Game.City.CityStatistic>`  
- `public abstract GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  
- `public abstract GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  
- `public abstract GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  
- `public abstract GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  
- `public abstract GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  
- `public abstract GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  
- `public abstract GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  
- `public abstract GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

