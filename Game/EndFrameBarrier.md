# Game.EndFrameBarrier

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Game.SafeCommandBufferSystem`  

## Code

```csharp
public class EndFrameBarrier : Game.SafeCommandBufferSystem
{
    private System.Diagnostics.Stopwatch m_Stopwatch;
    private Unity.Jobs.JobHandle <producerHandle>k__BackingField;
    private System.Single <lastElapsedTime>k__BackingField;

    public Unity.Jobs.JobHandle producerHandle { get; private set; }
    public System.Single lastElapsedTime { get; private set; }
    public System.Single currentElapsedTime { get; }

    public EndFrameBarrier();

    public System.Void AddJobHandleForProducer(Unity.Jobs.JobHandle producerJob);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Diagnostics.Stopwatch m_Stopwatch`  

```csharp
private System.Diagnostics.Stopwatch m_Stopwatch;
```

- `private Unity.Jobs.JobHandle <producerHandle>k__BackingField`  

```csharp
private Unity.Jobs.JobHandle <producerHandle>k__BackingField;
```

- `private System.Single <lastElapsedTime>k__BackingField`  

```csharp
private System.Single <lastElapsedTime>k__BackingField;
```


## Properties

- `public Unity.Jobs.JobHandle producerHandle { get; private set }`  

```csharp
public Unity.Jobs.JobHandle producerHandle { get; private set; }
```

- `public System.Single lastElapsedTime { get; private set }`  

```csharp
public System.Single lastElapsedTime { get; private set; }
```

- `public System.Single currentElapsedTime { get }`  

```csharp
public System.Single currentElapsedTime { get; }
```


## Constructors

- `public EndFrameBarrier()`  

```csharp
[Preserve]
	public EndFrameBarrier()
	{
	}
```


## Methods

- `public AddJobHandleForProducer(Unity.Jobs.JobHandle producerJob) : System.Void`  

```csharp
public new void AddJobHandleForProducer(JobHandle producerJob)
	{
		producerHandle = JobHandle.CombineDependencies(producerHandle, producerJob);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_Stopwatch = new Stopwatch();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Stopwatch.Stop();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_Stopwatch.Stop();
		lastElapsedTime = (float)m_Stopwatch.ElapsedTicks / (float)Stopwatch.Frequency;
		m_Stopwatch.Reset();
		producerHandle.Complete();
		producerHandle = default(JobHandle);
		m_Stopwatch.Start();
		base.OnUpdate();
	}
```


