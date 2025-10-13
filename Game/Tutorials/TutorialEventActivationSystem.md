# Game.Tutorials.TutorialEventActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TutorialEventActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ActivationQueue;
    private Unity.Jobs.JobHandle m_InputDependencies;

    public TutorialEventActivationSystem();

    public System.Void AddQueueWriter(Unity.Jobs.JobHandle dependency);
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> GetQueue(Unity.Jobs.JobHandle& dependency);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ActivationQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ActivationQueue;
```

- `private Unity.Jobs.JobHandle m_InputDependencies`  

```csharp
private Unity.Jobs.JobHandle m_InputDependencies;
```


## Constructors

- `public TutorialEventActivationSystem()`  

```csharp
[Preserve]
	public TutorialEventActivationSystem()
	{
	}
```


## Methods

- `public AddQueueWriter(Unity.Jobs.JobHandle dependency) : System.Void`  

```csharp
public void AddQueueWriter(JobHandle dependency)
	{
		m_InputDependencies = JobHandle.CombineDependencies(m_InputDependencies, dependency);
	}
```

- `public GetQueue(Unity.Jobs.JobHandle& dependency) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  

```csharp
public NativeQueue<Entity> GetQueue(out JobHandle dependency)
	{
		dependency = m_InputDependencies;
		return m_ActivationQueue;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_BarrierSystem = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_ActivationQueue = new NativeQueue<Entity>(Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		m_ActivationQueue.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_InputDependencies.Complete();
		EntityCommandBuffer entityCommandBuffer = m_BarrierSystem.CreateCommandBuffer();
		Entity item;
		while (m_ActivationQueue.TryDequeue(out item))
		{
			entityCommandBuffer.AddComponent<TutorialActivated>(item);
		}
	}
```


