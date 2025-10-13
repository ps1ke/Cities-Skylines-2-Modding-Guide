# Game.Simulation.CountConsumptionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public class CountConsumptionSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Collections.NativeArray<System.Int32> m_Consumptions;
    private Unity.Collections.NativeArray<System.Int32> m_ConsumptionAccumulator;
    private Unity.Jobs.JobHandle m_ReadDeps;
    private Unity.Jobs.JobHandle m_WriteDeps;
    private Unity.Jobs.JobHandle m_CopyDeps;
    public static readonly System.Int32 kUpdatesPerDay;

    public CountConsumptionSystem();

    public System.Void AddConsumptionReader(Unity.Jobs.JobHandle deps);
    public System.Void AddConsumptionWriter(Unity.Jobs.JobHandle deps);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetConsumptionAccumulator(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetConsumptions(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Collections.NativeArray<System.Int32> m_Consumptions`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Consumptions;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ConsumptionAccumulator`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ConsumptionAccumulator;
```

- `private Unity.Jobs.JobHandle m_ReadDeps`  

```csharp
private Unity.Jobs.JobHandle m_ReadDeps;
```

- `private Unity.Jobs.JobHandle m_WriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_WriteDeps;
```

- `private Unity.Jobs.JobHandle m_CopyDeps`  

```csharp
private Unity.Jobs.JobHandle m_CopyDeps;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public CountConsumptionSystem()`  

```csharp
[Preserve]
	public CountConsumptionSystem()
	{
	}
```


## Methods

- `public AddConsumptionReader(Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
public void AddConsumptionReader(JobHandle deps)
	{
		m_ReadDeps = JobHandle.CombineDependencies(m_ReadDeps, deps);
	}
```

- `public AddConsumptionWriter(Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
public void AddConsumptionWriter(JobHandle deps)
	{
		m_WriteDeps = JobHandle.CombineDependencies(m_WriteDeps, deps);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetConsumptionAccumulator(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetConsumptionAccumulator(out JobHandle deps)
	{
		deps = m_WriteDeps;
		return m_ConsumptionAccumulator;
	}
```

- `public GetConsumptions(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetConsumptions(out JobHandle deps)
	{
		deps = m_CopyDeps;
		return m_Consumptions;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_Consumptions = new NativeArray<int>(EconomyUtils.ResourceCount, Allocator.Persistent);
		m_ConsumptionAccumulator = new NativeArray<int>(EconomyUtils.ResourceCount, Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_ConsumptionAccumulator.Dispose();
		m_Consumptions.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		CopyConsumptionJob jobData = new CopyConsumptionJob
		{
			m_Accumulator = m_ConsumptionAccumulator,
			m_Consumptions = m_Consumptions
		};
		base.Dependency = jobData.Schedule(JobHandle.CombineDependencies(m_ReadDeps, m_WriteDeps));
		m_CopyDeps = base.Dependency;
		m_WriteDeps = base.Dependency;
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
		for (int i = 0; i < m_ConsumptionAccumulator.Length; i++)
		{
			m_ConsumptionAccumulator[i] = 0;
			m_Consumptions[i] = 0;
		}
	}
```


## Nested types

- `Game.Simulation.CountConsumptionSystem+CopyConsumptionJob`  

