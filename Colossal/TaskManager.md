# Colossal.TaskManager

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class TaskManager
{
    private Colossal.OnNotifyProgress onNotifyProgress;
    private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, Colossal.ProgressTracker> m_TaskProgress;
    private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.ProgressTracker+Group, System.Int32> m_TaskGroups;
    private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.Task> m_TaskRegistry;
    private readonly Colossal.TaskManager+TaskQueue m_TaskQueue;
    private readonly Colossal.TaskManager+TaskCompletionSources <taskCompletionSources>k__BackingField;
    private readonly Colossal.TaskProgress <progress>k__BackingField;
    private static Colossal.TaskManager s_Instance;
    private static Colossal.Logging.ILog log;

    public static Colossal.TaskManager instance { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.ProgressTracker> taskProgress { get; }
    public System.Collections.Generic.IReadOnlyDictionary<Colossal.ProgressTracker+Group, System.Int32> taskGroups { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Threading.Tasks.Task> taskRegistry { get; }
    public Colossal.TaskManager+TaskQueue taskQueue { get; }
    public Colossal.TaskManager+TaskCompletionSources taskCompletionSources { get; }
    public Colossal.TaskProgress progress { get; }

    public TaskManager();

    private System.Void <.ctor>b__28_0(Colossal.ProgressTracker info);
    public System.Threading.Tasks.Task Clear();
    public System.Threading.Tasks.Task Complete(System.String name);
    public System.Threading.Tasks.Task CompleteAndClear();
    public System.Threading.Tasks.Task EnqueueTask(System.String name, System.Func<System.Threading.Tasks.Task> task, System.Int32 cap);
    public System.Single GetTaskProgress(Colossal.ProgressTracker+Group group);
    public System.Single GetTaskProgress(System.String taskName);
    public System.Void Prune();
    public System.Void ScheduleGroup(Colossal.ProgressTracker+Group group, System.Int32 count);
    public System.Threading.Tasks.Task SharedTask(System.String name, System.Func<System.Threading.Tasks.Task> func);
    public System.Threading.Tasks.Task SharedTask(System.String name, System.Func<System.Threading.CancellationToken, System.Threading.Tasks.Task> func, System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task SharedTask<T>(System.String name, System.Func<T, System.Threading.CancellationToken, System.Threading.Tasks.Task> func, T arg, System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task SharedTask<T1, T2>(System.String name, System.Func<T1, T2, System.Threading.CancellationToken, System.Threading.Tasks.Task> func, T1 arg1, T2 arg2, System.Threading.CancellationToken token);
    public T TrackedTask<T>(System.String name, T task);
    public System.Boolean TryGetTaskProgress(System.String taskName, System.Single& progress);
}
```


## Fields

- `private Colossal.OnNotifyProgress onNotifyProgress`  

```csharp
private Colossal.OnNotifyProgress onNotifyProgress;
```

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, Colossal.ProgressTracker> m_TaskProgress`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, Colossal.ProgressTracker> m_TaskProgress;
```

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.ProgressTracker+Group, System.Int32> m_TaskGroups`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.ProgressTracker+Group, System.Int32> m_TaskGroups;
```

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.Task> m_TaskRegistry`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.Task> m_TaskRegistry;
```

- `private readonly Colossal.TaskManager+TaskQueue m_TaskQueue`  

```csharp
private readonly Colossal.TaskManager+TaskQueue m_TaskQueue;
```

- `private readonly Colossal.TaskManager+TaskCompletionSources <taskCompletionSources>k__BackingField`  

```csharp
private readonly Colossal.TaskManager+TaskCompletionSources <taskCompletionSources>k__BackingField;
```

- `private readonly Colossal.TaskProgress <progress>k__BackingField`  

```csharp
private readonly Colossal.TaskProgress <progress>k__BackingField;
```

- `private static Colossal.TaskManager s_Instance`  

```csharp
private static Colossal.TaskManager s_Instance;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Properties

- `public static Colossal.TaskManager instance { get }`  

```csharp
public static Colossal.TaskManager instance { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.ProgressTracker> taskProgress { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.ProgressTracker> taskProgress { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<Colossal.ProgressTracker+Group, System.Int32> taskGroups { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<Colossal.ProgressTracker+Group, System.Int32> taskGroups { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Threading.Tasks.Task> taskRegistry { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Threading.Tasks.Task> taskRegistry { get; }
```

- `public Colossal.TaskManager+TaskQueue taskQueue { get }`  

```csharp
public Colossal.TaskManager+TaskQueue taskQueue { get; }
```

- `public Colossal.TaskManager+TaskCompletionSources taskCompletionSources { get }`  

```csharp
public Colossal.TaskManager+TaskCompletionSources taskCompletionSources { get; }
```

- `public Colossal.TaskProgress progress { get }`  

```csharp
public Colossal.TaskProgress progress { get; }
```


## Constructors

- `public TaskManager()`  

```csharp
public TaskManager();
```


## Methods

- `private <.ctor>b__28_0(Colossal.ProgressTracker info) : System.Void`  

```csharp
private System.Void <.ctor>b__28_0(Colossal.ProgressTracker info);
```

- `public Clear() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Clear();
```

- `public Complete(System.String name) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Complete(System.String name);
```

- `public CompleteAndClear() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task CompleteAndClear();
```

- `public EnqueueTask(System.String name, System.Func<System.Threading.Tasks.Task> task, System.Int32 cap = 0) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task EnqueueTask(System.String name, System.Func<System.Threading.Tasks.Task> task, System.Int32 cap);
```

- `public GetTaskProgress(Colossal.ProgressTracker+Group group) : System.Single`  

```csharp
public System.Single GetTaskProgress(Colossal.ProgressTracker+Group group);
```

- `public GetTaskProgress(System.String taskName) : System.Single`  

```csharp
public System.Single GetTaskProgress(System.String taskName);
```

- `public Prune() : System.Void`  

```csharp
public System.Void Prune();
```

- `public ScheduleGroup(Colossal.ProgressTracker+Group group, System.Int32 count) : System.Void`  

```csharp
public System.Void ScheduleGroup(Colossal.ProgressTracker+Group group, System.Int32 count);
```

- `public SharedTask(System.String name, System.Func<System.Threading.Tasks.Task> func) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SharedTask(System.String name, System.Func<System.Threading.Tasks.Task> func);
```

- `public SharedTask(System.String name, System.Func<System.Threading.CancellationToken, System.Threading.Tasks.Task> func, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SharedTask(System.String name, System.Func<System.Threading.CancellationToken, System.Threading.Tasks.Task> func, System.Threading.CancellationToken token);
```

- `public SharedTask<T>(System.String name, System.Func<T, System.Threading.CancellationToken, System.Threading.Tasks.Task> func, T arg, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SharedTask<T>(System.String name, System.Func<T, System.Threading.CancellationToken, System.Threading.Tasks.Task> func, T arg, System.Threading.CancellationToken token);
```

- `public SharedTask<T1, T2>(System.String name, System.Func<T1, T2, System.Threading.CancellationToken, System.Threading.Tasks.Task> func, T1 arg1, T2 arg2, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SharedTask<T1, T2>(System.String name, System.Func<T1, T2, System.Threading.CancellationToken, System.Threading.Tasks.Task> func, T1 arg1, T2 arg2, System.Threading.CancellationToken token);
```

- `public TrackedTask<T>(System.String name, T task) : T`  

```csharp
public T TrackedTask<T>(System.String name, T task);
```

- `public TryGetTaskProgress(System.String taskName, System.Single& progress) : System.Boolean`  

```csharp
public System.Boolean TryGetTaskProgress(System.String taskName, System.Single& progress);
```


## Events

- `onNotifyProgress` : `Colossal.OnNotifyProgress`  

```csharp
public event Colossal.OnNotifyProgress onNotifyProgress;
```


## Nested types

- `Colossal.TaskManager+TaskCompletionSources`  
- `Colossal.TaskManager+TaskQueue`  
- `Colossal.TaskManager+<>c`  
- `Colossal.TaskManager+<>c__DisplayClass35_0`  
- `Colossal.TaskManager+<>c__DisplayClass41_0`  
- `Colossal.TaskManager+<CompleteAndClear>d__39`  

