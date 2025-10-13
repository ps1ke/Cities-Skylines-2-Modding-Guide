# Game.Simulation.ElectricityStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IElectricityStatisticsSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityStatisticsSystem : Game.GameSystemBase, Game.Simulation.IElectricityStatisticsSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_ProducerGroup;
    private Unity.Entities.EntityQuery m_ConsumerGroup;
    private Unity.Entities.EntityQuery m_BatteryGroup;
    private Colossal.NativePerThreadSumInt m_Production;
    private Colossal.NativePerThreadSumInt m_Consumption;
    private Colossal.NativePerThreadSumInt m_FulfilledConsumption;
    private Colossal.NativePerThreadSumInt m_BatteryCharge;
    private Colossal.NativePerThreadSumInt m_BatteryCapacity;
    private System.Int32 m_LastProduction;
    private System.Int32 m_LastConsumption;
    private System.Int32 m_LastFulfilledConsumption;
    private System.Int32 m_LastBatteryCharge;
    private System.Int32 m_LastBatteryCapacity;
    private Game.Simulation.ElectricityStatisticsSystem+TypeHandle __TypeHandle;

    public System.Int32 production { get; }
    public System.Int32 consumption { get; }
    public System.Int32 fulfilledConsumption { get; }
    public System.Int32 batteryCharge { get; }
    public System.Int32 batteryCapacity { get; }

    public ElectricityStatisticsSystem();

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

- `private Unity.Entities.EntityQuery m_ProducerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ProducerGroup;
```

- `private Unity.Entities.EntityQuery m_ConsumerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerGroup;
```

- `private Unity.Entities.EntityQuery m_BatteryGroup`  

```csharp
private Unity.Entities.EntityQuery m_BatteryGroup;
```

- `private Colossal.NativePerThreadSumInt m_Production`  

```csharp
private Colossal.NativePerThreadSumInt m_Production;
```

- `private Colossal.NativePerThreadSumInt m_Consumption`  

```csharp
private Colossal.NativePerThreadSumInt m_Consumption;
```

- `private Colossal.NativePerThreadSumInt m_FulfilledConsumption`  

```csharp
private Colossal.NativePerThreadSumInt m_FulfilledConsumption;
```

- `private Colossal.NativePerThreadSumInt m_BatteryCharge`  

```csharp
private Colossal.NativePerThreadSumInt m_BatteryCharge;
```

- `private Colossal.NativePerThreadSumInt m_BatteryCapacity`  

```csharp
private Colossal.NativePerThreadSumInt m_BatteryCapacity;
```

- `private System.Int32 m_LastProduction`  

```csharp
private System.Int32 m_LastProduction;
```

- `private System.Int32 m_LastConsumption`  

```csharp
private System.Int32 m_LastConsumption;
```

- `private System.Int32 m_LastFulfilledConsumption`  

```csharp
private System.Int32 m_LastFulfilledConsumption;
```

- `private System.Int32 m_LastBatteryCharge`  

```csharp
private System.Int32 m_LastBatteryCharge;
```

- `private System.Int32 m_LastBatteryCapacity`  

```csharp
private System.Int32 m_LastBatteryCapacity;
```

- `private Game.Simulation.ElectricityStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityStatisticsSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 production { get }`  

```csharp
public System.Int32 production { get; }
```

- `public System.Int32 consumption { get }`  

```csharp
public System.Int32 consumption { get; }
```

- `public System.Int32 fulfilledConsumption { get }`  

```csharp
public System.Int32 fulfilledConsumption { get; }
```

- `public System.Int32 batteryCharge { get }`  

```csharp
public System.Int32 batteryCharge { get; }
```

- `public System.Int32 batteryCapacity { get }`  

```csharp
public System.Int32 batteryCapacity { get; }
```


## Constructors

- `public ElectricityStatisticsSystem()`  

```csharp
[Preserve]
	public ElectricityStatisticsSystem()
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
		return 127;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ProducerGroup = GetEntityQuery(ComponentType.ReadOnly<ElectricityProducer>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ConsumerGroup = GetEntityQuery(ComponentType.ReadOnly<ElectricityConsumer>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_BatteryGroup = GetEntityQuery(ComponentType.ReadOnly<Battery>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_Production = new NativePerThreadSumInt(Allocator.Persistent);
		m_Consumption = new NativePerThreadSumInt(Allocator.Persistent);
		m_FulfilledConsumption = new NativePerThreadSumInt(Allocator.Persistent);
		m_BatteryCharge = new NativePerThreadSumInt(Allocator.Persistent);
		m_BatteryCapacity = new NativePerThreadSumInt(Allocator.Persistent);
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
		m_Production.Dispose();
		m_Consumption.Dispose();
		m_FulfilledConsumption.Dispose();
		m_BatteryCharge.Dispose();
		m_BatteryCapacity.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_LastProduction = m_Production.Count;
		m_LastConsumption = m_Consumption.Count;
		m_LastFulfilledConsumption = m_FulfilledConsumption.Count;
		m_LastBatteryCharge = m_BatteryCharge.Count;
		m_LastBatteryCapacity = m_BatteryCapacity.Count;
		m_Production.Count = 0;
		m_Consumption.Count = 0;
		m_FulfilledConsumption.Count = 0;
		m_BatteryCharge.Count = 0;
		m_BatteryCapacity.Count = 0;
		JobHandle job = default(JobHandle);
		if (!m_ProducerGroup.IsEmptyIgnoreFilter)
		{
			job = JobChunkExtensions.ScheduleParallel(new CountElectricityProductionJob
			{
				m_ProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Production = m_Production.ToConcurrent()
			}, m_ProducerGroup, base.Dependency);
		}
		JobHandle job2 = default(JobHandle);
		if (!m_ConsumerGroup.IsEmptyIgnoreFilter)
		{
			job2 = JobChunkExtensions.ScheduleParallel(new CountElectricityConsumptionJob
			{
				m_ConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Consumption = m_Consumption.ToConcurrent(),
				m_FulfilledConsumption = m_FulfilledConsumption.ToConcurrent()
			}, m_ConsumerGroup, base.Dependency);
		}
		JobHandle job3 = default(JobHandle);
		if (!m_ConsumerGroup.IsEmptyIgnoreFilter)
		{
			job3 = JobChunkExtensions.ScheduleParallel(new CountBatteryCapacityJob
			{
				m_BatteryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Battery_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Charge = m_BatteryCharge.ToConcurrent(),
				m_Capacity = m_BatteryCapacity.ToConcurrent()
			}, m_BatteryGroup, base.Dependency);
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
		m_LastProduction = 0;
		m_LastConsumption = 0;
		m_LastFulfilledConsumption = 0;
		m_LastBatteryCharge = 0;
		m_LastBatteryCapacity = 0;
	}
```


## Nested types

- `Game.Simulation.ElectricityStatisticsSystem+CountElectricityProductionJob`  
- `Game.Simulation.ElectricityStatisticsSystem+CountElectricityConsumptionJob`  
- `Game.Simulation.ElectricityStatisticsSystem+CountBatteryCapacityJob`  
- `Game.Simulation.ElectricityStatisticsSystem+TypeHandle`  

