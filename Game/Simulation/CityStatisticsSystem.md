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
[Preserve]
	public CityStatisticsSystem()
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

- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  

```csharp
public void AddWriter(JobHandle writer)
	{
		m_Writers = JobHandle.CombineDependencies(m_Writers, writer);
	}
```

- `public CompleteWriters() : System.Void`  

```csharp
public void CompleteWriters()
	{
		m_Writers.Complete();
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public DiscardStatistics() : System.Void`  

```csharp
public void DiscardStatistics()
	{
		m_Writers.Complete();
		m_StatisticsEventQueue.Clear();
	}
```

- `public GetLookup() : Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity>`  

```csharp
public NativeParallelHashMap<StatisticsKey, Entity> GetLookup()
	{
		return m_StatisticsLookup;
	}
```

- `public GetSafeStatisticsQueue(Unity.Jobs.JobHandle& deps) : Game.Simulation.CityStatisticsSystem+SafeStatisticQueue`  

```csharp
public SafeStatisticQueue GetSafeStatisticsQueue(out JobHandle deps)
	{
		deps = m_Writers;
		return new SafeStatisticQueue(m_StatisticsEventQueue, base.Enabled);
	}
```

- `public GetSampleFrameIndex(System.Int32 index) : System.UInt32`  

```csharp
public uint GetSampleFrameIndex(int index)
	{
		int num = (sampleCount - index - 1) * 8192;
		return m_LastSampleFrameIndex - (uint)num;
	}
```

- `public GetStatisticArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<Game.City.CityStatistic>`  

```csharp
public NativeArray<CityStatistic> GetStatisticArray(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		m_Writers.Complete();
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer))
			{
				return buffer.AsNativeArray();
			}
		}
		return new NativeArray<CityStatistic>(1, Allocator.Temp);
	}
```

- `public static GetStatisticDataArray(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetStatisticDataArray(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer))
			{
				NativeArray<int> result = new NativeArray<int>(buffer.Length, Allocator.Temp);
				for (int i = 0; i < buffer.Length; i++)
				{
					double num = Math.Round(buffer[i].m_TotalValue, MidpointRounding.AwayFromZero);
					result[i] = ((num > 2147483647.0) ? int.MaxValue : ((num < -2147483648.0) ? int.MinValue : ((int)num)));
				}
				return result;
			}
		}
		return new NativeArray<int>(1, Allocator.Temp);
	}
```

- `public GetStatisticDataArray(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetStatisticDataArray(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer))
			{
				NativeArray<int> result = new NativeArray<int>(buffer.Length, Allocator.Temp);
				for (int i = 0; i < buffer.Length; i++)
				{
					double num = Math.Round(buffer[i].m_TotalValue, MidpointRounding.AwayFromZero);
					result[i] = ((num > 2147483647.0) ? int.MaxValue : ((num < -2147483648.0) ? int.MinValue : ((int)num)));
				}
				return result;
			}
		}
		return new NativeArray<int>(1, Allocator.Temp);
	}
```

- `public GetStatisticDataArray(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetStatisticDataArray(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer))
			{
				NativeArray<int> result = new NativeArray<int>(buffer.Length, Allocator.Temp);
				for (int i = 0; i < buffer.Length; i++)
				{
					double num = Math.Round(buffer[i].m_TotalValue, MidpointRounding.AwayFromZero);
					result[i] = ((num > 2147483647.0) ? int.MaxValue : ((num < -2147483648.0) ? int.MinValue : ((int)num)));
				}
				return result;
			}
		}
		return new NativeArray<int>(1, Allocator.Temp);
	}
```

- `public static GetStatisticDataArrayLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public NativeArray<long> GetStatisticDataArrayLong(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer))
			{
				NativeArray<long> result = new NativeArray<long>(buffer.Length, Allocator.Temp);
				for (int i = 0; i < buffer.Length; i++)
				{
					double num = Math.Round(buffer[i].m_TotalValue, MidpointRounding.AwayFromZero);
					result[i] = ((num > 9.223372036854776E+18) ? long.MaxValue : ((num < -9.223372036854776E+18) ? long.MinValue : ((long)num)));
				}
				return result;
			}
		}
		return new NativeArray<long>(1, Allocator.Temp);
	}
```

- `public GetStatisticDataArrayLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public NativeArray<long> GetStatisticDataArrayLong(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer))
			{
				NativeArray<long> result = new NativeArray<long>(buffer.Length, Allocator.Temp);
				for (int i = 0; i < buffer.Length; i++)
				{
					double num = Math.Round(buffer[i].m_TotalValue, MidpointRounding.AwayFromZero);
					result[i] = ((num > 9.223372036854776E+18) ? long.MaxValue : ((num < -9.223372036854776E+18) ? long.MinValue : ((long)num)));
				}
				return result;
			}
		}
		return new NativeArray<long>(1, Allocator.Temp);
	}
```

- `public GetStatisticDataArrayLong(Game.City.StatisticType type, System.Int32 parameter = 0) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public NativeArray<long> GetStatisticDataArrayLong(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer))
			{
				NativeArray<long> result = new NativeArray<long>(buffer.Length, Allocator.Temp);
				for (int i = 0; i < buffer.Length; i++)
				{
					double num = Math.Round(buffer[i].m_TotalValue, MidpointRounding.AwayFromZero);
					result[i] = ((num > 9.223372036854776E+18) ? long.MaxValue : ((num < -9.223372036854776E+18) ? long.MinValue : ((long)num)));
				}
				return result;
			}
		}
		return new NativeArray<long>(1, Allocator.Temp);
	}
```

- `public GetStatisticsEventQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.City.StatisticsEvent>`  

```csharp
public NativeQueue<StatisticsEvent> GetStatisticsEventQueue(out JobHandle deps)
	{
		Assert.IsTrue(base.Enabled, "Can not write to queue when system isn't running");
		deps = m_Writers;
		return m_StatisticsEventQueue;
	}
```

- `public static GetStatisticValue(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  

```csharp
public int GetStatisticValue(StatisticType type, int parameter = 0)
	{
		long statisticValueLong = GetStatisticValueLong(type, parameter);
		if (statisticValueLong <= int.MaxValue)
		{
			if (statisticValueLong >= int.MinValue)
			{
				return (int)statisticValueLong;
			}
			return int.MinValue;
		}
		return int.MaxValue;
	}
```

- `public GetStatisticValue(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  

```csharp
public int GetStatisticValue(StatisticType type, int parameter = 0)
	{
		long statisticValueLong = GetStatisticValueLong(type, parameter);
		if (statisticValueLong <= int.MaxValue)
		{
			if (statisticValueLong >= int.MinValue)
			{
				return (int)statisticValueLong;
			}
			return int.MinValue;
		}
		return int.MaxValue;
	}
```

- `public GetStatisticValue(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int32`  

```csharp
public int GetStatisticValue(StatisticType type, int parameter = 0)
	{
		long statisticValueLong = GetStatisticValueLong(type, parameter);
		if (statisticValueLong <= int.MaxValue)
		{
			if (statisticValueLong >= int.MinValue)
			{
				return (int)statisticValueLong;
			}
			return int.MinValue;
		}
		return int.MaxValue;
	}
```

- `private static GetStatisticValueDouble(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Double`  

```csharp
private double GetStatisticValueDouble(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		m_Writers.Complete();
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer) && buffer.Length > 0)
			{
				return Math.Round(buffer[buffer.Length - 1].m_TotalValue, MidpointRounding.AwayFromZero);
			}
		}
		return 0.0;
	}
```

- `private GetStatisticValueDouble(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Double`  

```csharp
private double GetStatisticValueDouble(StatisticType type, int parameter = 0)
	{
		StatisticsKey key = new StatisticsKey(type, parameter);
		m_Writers.Complete();
		if (m_StatisticsLookup.ContainsKey(key))
		{
			Entity entity = m_StatisticsLookup[key];
			if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<CityStatistic> buffer) && buffer.Length > 0)
			{
				return Math.Round(buffer[buffer.Length - 1].m_TotalValue, MidpointRounding.AwayFromZero);
			}
		}
		return 0.0;
	}
```

- `public static GetStatisticValueLong(Unity.Collections.NativeParallelHashMap<Game.Simulation.CityStatisticsSystem+StatisticsKey, Unity.Entities.Entity> statisticsLookup, Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

```csharp
public long GetStatisticValueLong(StatisticType type, int parameter = 0)
	{
		double statisticValueDouble = GetStatisticValueDouble(type, parameter);
		if (!(statisticValueDouble > 9.223372036854776E+18))
		{
			if (!(statisticValueDouble < -9.223372036854776E+18))
			{
				return (long)statisticValueDouble;
			}
			return long.MinValue;
		}
		return long.MaxValue;
	}
```

- `public GetStatisticValueLong(Unity.Entities.BufferLookup<Game.City.CityStatistic> stats, Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

```csharp
public long GetStatisticValueLong(StatisticType type, int parameter = 0)
	{
		double statisticValueDouble = GetStatisticValueDouble(type, parameter);
		if (!(statisticValueDouble > 9.223372036854776E+18))
		{
			if (!(statisticValueDouble < -9.223372036854776E+18))
			{
				return (long)statisticValueDouble;
			}
			return long.MinValue;
		}
		return long.MaxValue;
	}
```

- `public GetStatisticValueLong(Game.City.StatisticType type, System.Int32 parameter = 0) : System.Int64`  

```csharp
public long GetStatisticValueLong(StatisticType type, int parameter = 0)
	{
		double statisticValueDouble = GetStatisticValueDouble(type, parameter);
		if (!(statisticValueDouble > 9.223372036854776E+18))
		{
			if (!(statisticValueDouble < -9.223372036854776E+18))
			{
				return (long)statisticValueDouble;
			}
			return long.MinValue;
		}
		return long.MaxValue;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 8192;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 0;
	}
```

- `private InitializeLookup() : System.Void`  

```csharp
private void InitializeLookup()
	{
		m_StatisticsLookup.Clear();
		NativeArray<Entity> nativeArray = m_StatisticsPrefabQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<StatisticsData> nativeArray2 = m_StatisticsPrefabQuery.ToComponentDataArray<StatisticsData>(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			StatisticType statisticType = nativeArray2[i].m_StatisticType;
			if (base.EntityManager.TryGetBuffer(nativeArray[i], isReadOnly: true, out DynamicBuffer<StatisticParameterData> buffer))
			{
				for (int j = 0; j < buffer.Length; j++)
				{
					m_StatisticsLookup.Add(new StatisticsKey(statisticType, buffer[j].m_Value), Entity.Null);
				}
			}
			else
			{
				m_StatisticsLookup.Add(new StatisticsKey(statisticType, 0), Entity.Null);
			}
		}
		NativeArray<Entity> nativeArray3 = m_StatisticsQuery.ToEntityArray(Allocator.TempJob);
		bool flag = true;
		for (int k = 0; k < nativeArray3.Length; k++)
		{
			if (!base.EntityManager.TryGetComponent<PrefabRef>(nativeArray3[k], out var component))
			{
				continue;
			}
			int num = 0;
			if (base.EntityManager.TryGetComponent<StatisticParameter>(nativeArray3[k], out var component2))
			{
				num = component2.m_Value;
			}
			if (!base.EntityManager.TryGetBuffer(component.m_Prefab, isReadOnly: true, out DynamicBuffer<StatisticParameterData> buffer2))
			{
				continue;
			}
			flag = false;
			for (int l = 0; l < buffer2.Length; l++)
			{
				if (num == buffer2[l].m_Value)
				{
					flag = true;
					break;
				}
			}
			if (!flag)
			{
				break;
			}
		}
		if (flag)
		{
			for (int m = 0; m < nativeArray3.Length; m++)
			{
				if (base.EntityManager.TryGetComponent<PrefabRef>(nativeArray3[m], out var component3) && base.EntityManager.TryGetComponent<StatisticsData>(component3.m_Prefab, out var component4))
				{
					int parameter = 0;
					if (base.EntityManager.TryGetComponent<StatisticParameter>(nativeArray3[m], out var component5))
					{
						parameter = component5.m_Value;
					}
					StatisticsKey key = new StatisticsKey(component4.m_StatisticType, parameter);
					if (m_StatisticsLookup.ContainsKey(key))
					{
						m_StatisticsLookup[key] = nativeArray3[m];
					}
				}
			}
		}
		else
		{
			base.EntityManager.DestroyEntity(m_StatisticsQuery);
			m_SampleCount = 0;
			m_StatisticsEventQueue.Clear();
		}
		nativeArray3.Dispose();
		NativeKeyValueArrays<StatisticsKey, Entity> keyValueArrays = m_StatisticsLookup.GetKeyValueArrays(Allocator.Temp);
		for (int n = 0; n < keyValueArrays.Length; n++)
		{
			if (!(keyValueArrays.Values[n] == Entity.Null))
			{
				continue;
			}
			StatisticsKey key2 = keyValueArrays.Keys[n];
			StatisticType type = key2.type;
			for (int num2 = 0; num2 < nativeArray.Length; num2++)
			{
				Entity entity = nativeArray[num2];
				DynamicBuffer<StatisticParameterData> buffer3;
				bool flag2 = base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out buffer3);
				if (!base.EntityManager.TryGetComponent<StatisticsData>(entity, out var component6) || component6.m_StatisticType != type)
				{
					continue;
				}
				if (flag2)
				{
					bool flag3 = false;
					for (int num3 = 0; num3 < buffer3.Length; num3++)
					{
						if (buffer3[num3].m_Value == key2.parameter)
						{
							flag3 = true;
						}
					}
					if (!flag3)
					{
						continue;
					}
				}
				ArchetypeData componentData = base.EntityManager.GetComponentData<ArchetypeData>(entity);
				m_StatisticsLookup[key2] = StatisticsPrefab.CreateInstance(base.World.EntityManager, entity, componentData, key2.parameter);
				break;
			}
		}
		m_Initialized = true;
		nativeArray.Dispose();
		nativeArray2.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CountHouseholdDataSystem = base.World.GetOrCreateSystemManaged<CountHouseholdDataSystem>();
		m_StatisticsPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<StatisticsData>());
		m_StatisticsQuery = GetEntityQuery(ComponentType.ReadOnly<CityStatistic>());
		m_CityQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		RequireForUpdate(m_CityQuery);
		m_StatisticsLookup = new NativeParallelHashMap<StatisticsKey, Entity>(64, Allocator.Persistent);
		m_StatisticsEventQueue = new NativeQueue<StatisticsEvent>(Allocator.Persistent);
		base.Enabled = false;
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
		m_StatisticsLookup.Dispose();
		m_StatisticsEventQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_Initialized)
		{
			InitializeLookup();
		}
		JobHandle job = IJobExtensions.Schedule(new CityStatisticsJob
		{
			m_StatisticsEventQueue = m_StatisticsEventQueue,
			m_HouseholdData = m_CountHouseholdDataSystem.GetHouseholdCountData(),
			m_Tourisms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Tourism_RW_ComponentLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_Money = m_CitySystem.moneyAmount
		}, JobHandle.CombineDependencies(base.Dependency, m_Writers));
		JobHandle dependsOn = IJobExtensions.Schedule(new ProcessStatisticsJob
		{
			m_Statistics = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RW_BufferLookup, ref base.CheckedStateRef),
			m_StatisticsLookup = m_StatisticsLookup,
			m_Queue = m_StatisticsEventQueue
		}, JobHandle.CombineDependencies(job, base.Dependency));
		JobHandle dependency = IJobExtensions.Schedule(new ResetEntityJob
		{
			m_Money = m_CitySystem.moneyAmount,
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStats = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StatisticsData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Statistics = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RW_BufferLookup, ref base.CheckedStateRef),
			m_StatisticsLookup = m_StatisticsLookup
		}, dependsOn);
		base.Dependency = dependency;
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		AddWriter(base.Dependency);
		m_SampleCount++;
		m_LastSampleFrameIndex = m_SimulationSystem.frameIndex;
		eventStatisticsUpdated?.Invoke();
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		m_StatisticsLookup.Clear();
		InitializeLookup();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_SampleCount = 0;
		m_StatisticsEventQueue.Clear();
	}
```


## Nested types

- `Game.Simulation.CityStatisticsSystem+StatisticsKey`  
- `Game.Simulation.CityStatisticsSystem+SafeStatisticQueue`  
- `Game.Simulation.CityStatisticsSystem+CityStatisticsJob`  
- `Game.Simulation.CityStatisticsSystem+ProcessStatisticsJob`  
- `Game.Simulation.CityStatisticsSystem+ResetEntityJob`  
- `Game.Simulation.CityStatisticsSystem+TypeHandle`  

