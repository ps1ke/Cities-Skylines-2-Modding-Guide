# Game.Simulation.CityStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ICityStatisticsSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Unity.Entities.EntityQuery m_StatisticsPrefabQuery`  
- `private Unity.Entities.EntityQuery m_StatisticsQuery`  
- `private Unity.Entities.EntityQuery m_CityQuery`  
- `private Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> m_StatisticsLookup`  
- `private Unity.Collections.NativeQueue<Game.City.StatisticsEvent> m_StatisticsEventQueue`  
- `private Unity.Jobs.JobHandle m_Writers`  
- `private System.Boolean m_Initialized`  
- `private System.Int32 m_SampleCount`  
- `private System.UInt32 m_LastSampleFrameIndex`  
- `private System.Action <eventStatisticsUpdated>k__BackingField`  
- `private Game.Simulation.CityStatisticsSystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 kUpdatesPerDay`  

## Properties

- `public System.Int32 sampleCount { get }`  
- `public System.Action eventStatisticsUpdated { get; set }`  

## Constructors

- `public CityStatisticsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  
- `public CompleteWriters() : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public DiscardStatistics() : System.Void`  
- `public GetLookup() : Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity>`  
- `public GetSafeStatisticsQueue(Unity.Jobs.JobHandle& deps) : Game.Simulation.CityStatisticsSystem+SafeStatisticQueue`  
- `public GetSampleFrameIndex(System.Int32 index) : System.UInt32`  
- `public GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<Game.City.CityStatistic>`  
- `public static GetStatisticDataArray(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  
- `public static GetStatisticDataArrayLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  
- `public GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  
- `public GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  
- `public GetStatisticsEventQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.City.StatisticsEvent>`  
- `public static GetStatisticValue(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  
- `public GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  
- `public GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  
- `private static GetStatisticValueDouble(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Double`  
- `private GetStatisticValueDouble(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Double`  
- `public static GetStatisticValueLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  
- `public GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  
- `public GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `private InitializeLookup() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.CityStatisticsSystem+StatisticsKey`  
- `Game.Simulation.CityStatisticsSystem+SafeStatisticQueue`  
- `Game.Simulation.CityStatisticsSystem+CityStatisticsJob`  
- `Game.Simulation.CityStatisticsSystem+ProcessStatisticsJob`  
- `Game.Simulation.CityStatisticsSystem+ResetEntityJob`  
- `Game.Simulation.CityStatisticsSystem+TypeHandle`  

