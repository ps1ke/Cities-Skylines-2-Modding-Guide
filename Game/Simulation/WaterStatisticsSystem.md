# Game.Simulation.WaterStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IWaterStatisticsSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterStatisticsSystem : Game.GameSystemBase, Game.Simulation.IWaterStatisticsSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_PumpGroup;
    private Unity.Entities.EntityQuery m_OutletGroup;
    private Unity.Entities.EntityQuery m_ConsumerGroup;
    private Colossal.NativePerThreadSumInt m_FreshCapacity;
    private Colossal.NativePerThreadSumInt m_SewageCapacity;
    private Colossal.NativePerThreadSumInt m_Consumption;
    private Colossal.NativePerThreadSumInt m_FulfilledFreshConsumption;
    private Colossal.NativePerThreadSumInt m_FulfilledSewageConsumption;
    private System.Int32 m_LastFreshCapacity;
    private System.Int32 m_LastFreshConsumption;
    private System.Int32 m_LastFulfilledFreshConsumption;
    private System.Int32 m_LastSewageCapacity;
    private System.Int32 m_LastSewageConsumption;
    private System.Int32 m_LastFulfilledSewageConsumption;
    private Game.Simulation.WaterStatisticsSystem+TypeHandle __TypeHandle;

    public System.Int32 freshCapacity { get; }
    public System.Int32 freshConsumption { get; }
    public System.Int32 fulfilledFreshConsumption { get; }
    public System.Int32 sewageCapacity { get; }
    public System.Int32 sewageConsumption { get; }
    public System.Int32 fulfilledSewageConsumption { get; }

    public WaterStatisticsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PumpGroup`  

```csharp
private Unity.Entities.EntityQuery m_PumpGroup;
```

- `private Unity.Entities.EntityQuery m_OutletGroup`  

```csharp
private Unity.Entities.EntityQuery m_OutletGroup;
```

- `private Unity.Entities.EntityQuery m_ConsumerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerGroup;
```

- `private Colossal.NativePerThreadSumInt m_FreshCapacity`  

```csharp
private Colossal.NativePerThreadSumInt m_FreshCapacity;
```

- `private Colossal.NativePerThreadSumInt m_SewageCapacity`  

```csharp
private Colossal.NativePerThreadSumInt m_SewageCapacity;
```

- `private Colossal.NativePerThreadSumInt m_Consumption`  

```csharp
private Colossal.NativePerThreadSumInt m_Consumption;
```

- `private Colossal.NativePerThreadSumInt m_FulfilledFreshConsumption`  

```csharp
private Colossal.NativePerThreadSumInt m_FulfilledFreshConsumption;
```

- `private Colossal.NativePerThreadSumInt m_FulfilledSewageConsumption`  

```csharp
private Colossal.NativePerThreadSumInt m_FulfilledSewageConsumption;
```

- `private System.Int32 m_LastFreshCapacity`  

```csharp
private System.Int32 m_LastFreshCapacity;
```

- `private System.Int32 m_LastFreshConsumption`  

```csharp
private System.Int32 m_LastFreshConsumption;
```

- `private System.Int32 m_LastFulfilledFreshConsumption`  

```csharp
private System.Int32 m_LastFulfilledFreshConsumption;
```

- `private System.Int32 m_LastSewageCapacity`  

```csharp
private System.Int32 m_LastSewageCapacity;
```

- `private System.Int32 m_LastSewageConsumption`  

```csharp
private System.Int32 m_LastSewageConsumption;
```

- `private System.Int32 m_LastFulfilledSewageConsumption`  

```csharp
private System.Int32 m_LastFulfilledSewageConsumption;
```

- `private Game.Simulation.WaterStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterStatisticsSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 freshCapacity { get }`  

```csharp
public System.Int32 freshCapacity { get; }
```

- `public System.Int32 freshConsumption { get }`  

```csharp
public System.Int32 freshConsumption { get; }
```

- `public System.Int32 fulfilledFreshConsumption { get }`  

```csharp
public System.Int32 fulfilledFreshConsumption { get; }
```

- `public System.Int32 sewageCapacity { get }`  

```csharp
public System.Int32 sewageCapacity { get; }
```

- `public System.Int32 sewageConsumption { get }`  

```csharp
public System.Int32 sewageConsumption { get; }
```

- `public System.Int32 fulfilledSewageConsumption { get }`  

```csharp
public System.Int32 fulfilledSewageConsumption { get; }
```


## Constructors

- `public WaterStatisticsSystem()`  

```csharp
[Preserve]
	public WaterStatisticsSystem()
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

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 128;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 63;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PumpGroup = GetEntityQuery(ComponentType.ReadOnly<WaterPumpingStation>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_OutletGroup = GetEntityQuery(ComponentType.ReadOnly<SewageOutlet>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ConsumerGroup = GetEntityQuery(ComponentType.ReadOnly<WaterConsumer>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_FreshCapacity = new NativePerThreadSumInt(Allocator.Persistent);
		m_SewageCapacity = new NativePerThreadSumInt(Allocator.Persistent);
		m_Consumption = new NativePerThreadSumInt(Allocator.Persistent);
		m_FulfilledFreshConsumption = new NativePerThreadSumInt(Allocator.Persistent);
		m_FulfilledSewageConsumption = new NativePerThreadSumInt(Allocator.Persistent);
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
		m_FreshCapacity.Dispose();
		m_SewageCapacity.Dispose();
		m_Consumption.Dispose();
		m_FulfilledFreshConsumption.Dispose();
		m_FulfilledSewageConsumption.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_LastFreshCapacity = m_FreshCapacity.Count;
		m_LastFreshConsumption = m_Consumption.Count;
		m_LastFulfilledFreshConsumption = m_FulfilledFreshConsumption.Count;
		m_LastSewageCapacity = m_SewageCapacity.Count;
		m_LastSewageConsumption = m_Consumption.Count;
		m_LastFulfilledSewageConsumption = m_FulfilledSewageConsumption.Count;
		m_FreshCapacity.Count = 0;
		m_SewageCapacity.Count = 0;
		m_Consumption.Count = 0;
		m_FulfilledFreshConsumption.Count = 0;
		m_FulfilledSewageConsumption.Count = 0;
		JobHandle job = default(JobHandle);
		if (!m_PumpGroup.IsEmptyIgnoreFilter)
		{
			job = JobChunkExtensions.ScheduleParallel(new CountPumpCapacityJob
			{
				m_PumpType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterPumpingStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Capacity = m_FreshCapacity.ToConcurrent()
			}, m_PumpGroup, base.Dependency);
		}
		JobHandle job2 = default(JobHandle);
		if (!m_PumpGroup.IsEmptyIgnoreFilter)
		{
			job2 = JobChunkExtensions.ScheduleParallel(new CountOutletCapacityJob
			{
				m_OutletType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_SewageOutlet_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Capacity = m_SewageCapacity.ToConcurrent()
			}, m_OutletGroup, base.Dependency);
		}
		JobHandle job3 = default(JobHandle);
		if (!m_ConsumerGroup.IsEmptyIgnoreFilter)
		{
			job3 = JobChunkExtensions.ScheduleParallel(new CountWaterConsumptionJob
			{
				m_ConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Consumption = m_Consumption.ToConcurrent(),
				m_FulfilledFreshConsumption = m_FulfilledFreshConsumption.ToConcurrent(),
				m_FulfilledSewageConsumption = m_FulfilledSewageConsumption.ToConcurrent()
			}, m_ConsumerGroup, base.Dependency);
		}
		base.Dependency = JobHandle.CombineDependencies(job, job2, job3);
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
		m_LastFreshCapacity = 0;
		m_LastFreshConsumption = 0;
		m_LastFulfilledFreshConsumption = 0;
		m_LastSewageCapacity = 0;
		m_LastSewageConsumption = 0;
		m_LastFulfilledSewageConsumption = 0;
	}
```


## Nested types

- `Game.Simulation.WaterStatisticsSystem+CountPumpCapacityJob`  
- `Game.Simulation.WaterStatisticsSystem+CountOutletCapacityJob`  
- `Game.Simulation.WaterStatisticsSystem+CountWaterConsumptionJob`  
- `Game.Simulation.WaterStatisticsSystem+TypeHandle`  

