# Game.Simulation.CityStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ICityStatisticsSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityStatisticsSystem : Game.GameSystemBase, Game.Simulation.ICityStatisticsSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityQuery m_StatisticsPrefabQuery;
    private Unity.Entities.EntityQuery m_StatisticsQuery;
    private Unity.Entities.EntityQuery m_CityQuery;
    private Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> m_StatisticsLookup;
    private Unity.Collections.NativeQueue<Game.City.StatisticsEvent> m_StatisticsEventQueue;
    private Unity.Jobs.JobHandle m_Writers;
    private System.Boolean m_Initialized;
    private System.Int32 m_SampleCount;
    private System.UInt32 m_LastSampleFrameIndex;
    private System.Action <eventStatisticsUpdated>k__BackingField;
    private Game.Simulation.CityStatisticsSystem+TypeHandle __TypeHandle;
    public static const System.Int32 kUpdatesPerDay;

    public System.Int32 sampleCount { get; }
    public System.Action eventStatisticsUpdated { get; set; }

    public CityStatisticsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddWriter(Unity.Jobs.JobHandle writer);
    public System.Void CompleteWriters();
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void DiscardStatistics();
    public Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> GetLookup();
    public Game.Simulation.CityStatisticsSystem+SafeStatisticQueue GetSafeStatisticsQueue(Unity.Jobs.JobHandle& deps);
    public System.UInt32 GetSampleFrameIndex(System.Int32 index);
    public Unity.Collections.NativeArray<Game.City.CityStatistic> GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter);
    public static Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter);
    public static Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter);
    public Unity.Collections.NativeQueue<Game.City.StatisticsEvent> GetStatisticsEventQueue(Unity.Jobs.JobHandle& deps);
    public static System.Int32 GetStatisticValue(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public System.Int32 GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public System.Int32 GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter);
    private static System.Double GetStatisticValueDouble(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    private System.Double GetStatisticValueDouble(Game.City.StatisticType type, System.Int32 parameter);
    public static System.Int64 GetStatisticValueLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public System.Int64 GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
    public System.Int64 GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    private System.Void InitializeLookup();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityQuery m_StatisticsPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_StatisticsPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_StatisticsQuery`  

```csharp
private Unity.Entities.EntityQuery m_StatisticsQuery;
```

- `private Unity.Entities.EntityQuery m_CityQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityQuery;
```

- `private Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> m_StatisticsLookup`  

```csharp
private Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> m_StatisticsLookup;
```

- `private Unity.Collections.NativeQueue<Game.City.StatisticsEvent> m_StatisticsEventQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.City.StatisticsEvent> m_StatisticsEventQueue;
```

- `private Unity.Jobs.JobHandle m_Writers`  

```csharp
private Unity.Jobs.JobHandle m_Writers;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private System.Int32 m_SampleCount`  

```csharp
private System.Int32 m_SampleCount;
```

- `private System.UInt32 m_LastSampleFrameIndex`  

```csharp
private System.UInt32 m_LastSampleFrameIndex;
```

- `private System.Action <eventStatisticsUpdated>k__BackingField`  

```csharp
private System.Action <eventStatisticsUpdated>k__BackingField;
```

- `private Game.Simulation.CityStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CityStatisticsSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```


## Properties

- `public System.Int32 sampleCount { get }`  

```csharp
public System.Int32 sampleCount { get; }
```

- `public System.Action eventStatisticsUpdated { get; set }`  

```csharp
public System.Action eventStatisticsUpdated { get; set; }
```


## Constructors

- `public CityStatisticsSystem()`  

```csharp
public CityStatisticsSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  

```csharp
public System.Void AddWriter(Unity.Jobs.JobHandle writer);
```

- `public CompleteWriters() : System.Void`  

```csharp
public System.Void CompleteWriters();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public DiscardStatistics() : System.Void`  

```csharp
public System.Void DiscardStatistics();
```

- `public GetLookup() : Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity>`  

```csharp
public Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> GetLookup();
```

- `public GetSafeStatisticsQueue(Unity.Jobs.JobHandle& deps) : Game.Simulation.CityStatisticsSystem+SafeStatisticQueue`  

```csharp
public Game.Simulation.CityStatisticsSystem+SafeStatisticQueue GetSafeStatisticsQueue(Unity.Jobs.JobHandle& deps);
```

- `public GetSampleFrameIndex(System.Int32 index) : System.UInt32`  

```csharp
public System.UInt32 GetSampleFrameIndex(System.Int32 index);
```

- `public GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<Game.City.CityStatistic>`  

```csharp
public Unity.Collections.NativeArray<Game.City.CityStatistic> GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter);
```

- `public static GetStatisticDataArray(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public static Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter);
```

- `public static GetStatisticDataArrayLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public static Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public Unity.Collections.NativeArray<System.Int64> GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticsEventQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.City.StatisticsEvent>`  

```csharp
public Unity.Collections.NativeQueue<Game.City.StatisticsEvent> GetStatisticsEventQueue(Unity.Jobs.JobHandle& deps);
```

- `public static GetStatisticValue(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  

```csharp
public static System.Int32 GetStatisticValue(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  

```csharp
public System.Int32 GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  

```csharp
public System.Int32 GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter);
```

- `private static GetStatisticValueDouble(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Double`  

```csharp
private static System.Double GetStatisticValueDouble(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `private GetStatisticValueDouble(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Double`  

```csharp
private System.Double GetStatisticValueDouble(Game.City.StatisticType type, System.Int32 parameter);
```

- `public static GetStatisticValueLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

```csharp
public static System.Int64 GetStatisticValueLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

```csharp
public System.Int64 GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter);
```

- `public GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

```csharp
public System.Int64 GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
```

- `private InitializeLookup() : System.Void`  

```csharp
private System.Void InitializeLookup();
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
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

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.CityStatisticsSystem+StatisticsKey`  
- `Game.Simulation.CityStatisticsSystem+SafeStatisticQueue`  
- `Game.Simulation.CityStatisticsSystem+CityStatisticsJob`  
- `Game.Simulation.CityStatisticsSystem+ProcessStatisticsJob`  
- `Game.Simulation.CityStatisticsSystem+ResetEntityJob`  
- `Game.Simulation.CityStatisticsSystem+TypeHandle`  

