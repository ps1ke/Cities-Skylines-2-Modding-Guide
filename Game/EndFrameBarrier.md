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
public EndFrameBarrier();
```


## Methods

- `public AddJobHandleForProducer(Unity.Jobs.JobHandle producerJob) : System.Void`  

```csharp
public System.Void AddJobHandleForProducer(Unity.Jobs.JobHandle producerJob);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


