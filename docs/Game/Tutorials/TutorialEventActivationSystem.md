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
public TutorialEventActivationSystem();
```


## Methods

- `public AddQueueWriter(Unity.Jobs.JobHandle dependency) : System.Void`  

```csharp
public System.Void AddQueueWriter(Unity.Jobs.JobHandle dependency);
```

- `public GetQueue(Unity.Jobs.JobHandle& dependency) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> GetQueue(Unity.Jobs.JobHandle& dependency);
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


