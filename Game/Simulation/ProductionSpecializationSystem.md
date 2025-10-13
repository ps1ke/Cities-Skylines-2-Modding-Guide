# Game.Simulation.ProductionSpecializationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProductionSpecializationSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_BonusQuery;
    private Unity.Collections.NativeQueue<Game.Simulation.ProductionSpecializationSystem+ProducedResource> m_ProductionQueue;
    private Unity.Jobs.JobHandle m_QueueWriters;
    private Game.Simulation.ProductionSpecializationSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public ProductionSpecializationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeQueue<Game.Simulation.ProductionSpecializationSystem+ProducedResource> GetQueue(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
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

- `private Unity.Entities.EntityQuery m_BonusQuery`  

```csharp
private Unity.Entities.EntityQuery m_BonusQuery;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.ProductionSpecializationSystem+ProducedResource> m_ProductionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.ProductionSpecializationSystem+ProducedResource> m_ProductionQueue;
```

- `private Unity.Jobs.JobHandle m_QueueWriters`  

```csharp
private Unity.Jobs.JobHandle m_QueueWriters;
```

- `private Game.Simulation.ProductionSpecializationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ProductionSpecializationSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public ProductionSpecializationSystem()`  

```csharp
[Preserve]
	public ProductionSpecializationSystem()
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

- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddQueueWriter(JobHandle handle)
	{
		m_QueueWriters = JobHandle.CombineDependencies(m_QueueWriters, handle);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Simulation.ProductionSpecializationSystem+ProducedResource>`  

```csharp
public NativeQueue<ProducedResource> GetQueue(out JobHandle deps)
	{
		deps = m_QueueWriters;
		return m_ProductionQueue;
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
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_BonusQuery = GetEntityQuery(ComponentType.ReadOnly<SpecializationBonus>());
		m_ProductionQueue = new NativeQueue<ProducedResource>(Allocator.Persistent);
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
		base.OnDestroy();
		m_ProductionQueue.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		SpecializationJob jobData = new SpecializationJob
		{
			m_Bonuses = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_SpecializationBonus_RW_BufferLookup, ref base.CheckedStateRef),
			m_Queue = m_ProductionQueue,
			m_City = m_CitySystem.City
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(m_QueueWriters, base.Dependency));
		m_QueueWriters = base.Dependency;
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if ((context.purpose == Purpose.NewGame || context.purpose == Purpose.LoadGame) && m_BonusQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddBuffer<SpecializationBonus>(m_CitySystem.City);
		}
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
		m_ProductionQueue.Clear();
	}
```


## Nested types

- `Game.Simulation.ProductionSpecializationSystem+ProducedResource`  
- `Game.Simulation.ProductionSpecializationSystem+SpecializationJob`  
- `Game.Simulation.ProductionSpecializationSystem+TypeHandle`  

