# Game.Simulation.XPSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IXPSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class XPSystem : Game.GameSystemBase, Game.Simulation.IXPSystem
{
    private Unity.Collections.NativeQueue<Game.Simulation.XPMessage> m_XPMessages;
    private Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue;
    private Unity.Jobs.JobHandle m_QueueWriters;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.XPSystem+TypeHandle __TypeHandle;

    public XPSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeQueue<Game.Simulation.XPGain> GetQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void TransferMessages(Game.Simulation.IXPMessageHandler handler);
}
```


## Fields

- `private Unity.Collections.NativeQueue<Game.Simulation.XPMessage> m_XPMessages`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.XPMessage> m_XPMessages;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue;
```

- `private Unity.Jobs.JobHandle m_QueueWriters`  

```csharp
private Unity.Jobs.JobHandle m_QueueWriters;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.XPSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.XPSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public XPSystem()`  

```csharp
[Preserve]
	public XPSystem()
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

- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Simulation.XPGain>`  

```csharp
public NativeQueue<XPGain> GetQueue(out JobHandle deps)
	{
		deps = m_QueueWriters;
		return m_XPQueue;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_XPMessages = new NativeQueue<XPMessage>(Allocator.Persistent);
		m_XPQueue = new NativeQueue<XPGain>(Allocator.Persistent);
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
		m_XPQueue.Dispose();
		m_XPMessages.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!(m_CitySystem.City == Entity.Null))
		{
			XPQueueProcessJob jobData = new XPQueueProcessJob
			{
				m_City = m_CitySystem.City,
				m_FrameIndex = m_SimulationSystem.frameIndex,
				m_XPMessages = m_XPMessages,
				m_XPQueue = m_XPQueue,
				m_CityXPs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_XP_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(m_QueueWriters, base.Dependency));
			m_QueueWriters = base.Dependency;
		}
	}
```

- `public TransferMessages(Game.Simulation.IXPMessageHandler handler) : System.Void`  

```csharp
public void TransferMessages(IXPMessageHandler handler)
	{
		base.Dependency.Complete();
		while (m_XPMessages.Count > 0)
		{
			XPMessage message = m_XPMessages.Dequeue();
			handler.AddMessage(message);
		}
	}
```


## Nested types

- `Game.Simulation.XPSystem+XPQueueProcessJob`  
- `Game.Simulation.XPSystem+TypeHandle`  

