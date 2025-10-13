# Colossal.AssetPipeline.MainThreadDispatcher

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class MainThreadDispatcher
{
    private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.MainThreadDispatcher+Task> m_DispatchQueue;
    private System.Threading.ManualResetEvent m_DataEvent;

    public System.Int32 pendingTasksCount { get; }
    public System.Boolean hasPendingTasks { get; }

    public MainThreadDispatcher();

    private System.Void AddTask(Colossal.AssetPipeline.MainThreadDispatcher+Task task);
    public Colossal.AssetPipeline.MainThreadDispatcher+Task Dispatch(System.Action action);
    public Colossal.AssetPipeline.MainThreadDispatcher+Task<T> Dispatch<T>(System.Func<T> func);
    public System.Void ProcessTasks();
}
```


## Fields

- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.MainThreadDispatcher+Task> m_DispatchQueue`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.MainThreadDispatcher+Task> m_DispatchQueue;
```

- `private System.Threading.ManualResetEvent m_DataEvent`  

```csharp
private System.Threading.ManualResetEvent m_DataEvent;
```


## Properties

- `public System.Int32 pendingTasksCount { get }`  

```csharp
public System.Int32 pendingTasksCount { get; }
```

- `public System.Boolean hasPendingTasks { get }`  

```csharp
public System.Boolean hasPendingTasks { get; }
```


## Constructors

- `public MainThreadDispatcher()`  

```csharp
public MainThreadDispatcher();
```


## Methods

- `private AddTask(Colossal.AssetPipeline.MainThreadDispatcher+Task task) : System.Void`  

```csharp
private System.Void AddTask(Colossal.AssetPipeline.MainThreadDispatcher+Task task);
```

- `public Dispatch(System.Action action) : Colossal.AssetPipeline.MainThreadDispatcher+Task`  

```csharp
public Colossal.AssetPipeline.MainThreadDispatcher+Task Dispatch(System.Action action);
```

- `public Dispatch<T>(System.Func<T> func) : Colossal.AssetPipeline.MainThreadDispatcher+Task<T>`  

```csharp
public Colossal.AssetPipeline.MainThreadDispatcher+Task<T> Dispatch<T>(System.Func<T> func);
```

- `public ProcessTasks() : System.Void`  

```csharp
public System.Void ProcessTasks();
```


## Nested types

- `Colossal.AssetPipeline.MainThreadDispatcher+Task`  
- `Colossal.AssetPipeline.MainThreadDispatcher+Task<T>`  

