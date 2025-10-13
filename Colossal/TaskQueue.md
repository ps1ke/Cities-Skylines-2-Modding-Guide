# Colossal.TaskManager+TaskQueue

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<System.String>`, `System.Collections.IEnumerable`  

## Code

```csharp
public class TaskQueue : System.Collections.Generic.IEnumerable<System.String>, System.Collections.IEnumerable
{
    private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Collections.Concurrent.ConcurrentQueue<System.Func<System.Threading.Tasks.Task>>> m_TaskQueues;
    private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>> m_CompletionSources;
    private readonly System.Collections.Concurrent.ConcurrentBag<System.String> m_RunningTasks;
    private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_CompletionSource;

    public System.Int32 count { get; }

    public TaskQueue();

    public System.Threading.Tasks.Task Complete(System.String name);
    public System.Threading.Tasks.Task Complete();
    public System.Threading.Tasks.Task Enqueue(System.String name, System.Func<System.Threading.Tasks.Task> taskFunc, System.Int32 cap);
    public System.Collections.Generic.IEnumerator<System.String> GetEnumerator();
    public System.Int32 GetPendingCount(System.String name);
    private System.Threading.Tasks.Task RunNextTask(System.String name);
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
}
```


## Fields

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Collections.Concurrent.ConcurrentQueue<System.Func<System.Threading.Tasks.Task>>> m_TaskQueues`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Collections.Concurrent.ConcurrentQueue<System.Func<System.Threading.Tasks.Task>>> m_TaskQueues;
```

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>> m_CompletionSources`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>> m_CompletionSources;
```

- `private readonly System.Collections.Concurrent.ConcurrentBag<System.String> m_RunningTasks`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentBag<System.String> m_RunningTasks;
```

- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_CompletionSource`  

```csharp
private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_CompletionSource;
```


## Properties

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```


## Constructors

- `public TaskQueue()`  

```csharp
public TaskQueue();
```


## Methods

- `public Complete(System.String name) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Complete(System.String name);
```

- `public Complete() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Complete();
```

- `public Enqueue(System.String name, System.Func<System.Threading.Tasks.Task> taskFunc, System.Int32 cap = 0) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Enqueue(System.String name, System.Func<System.Threading.Tasks.Task> taskFunc, System.Int32 cap);
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<System.String>`  

```csharp
public System.Collections.Generic.IEnumerator<System.String> GetEnumerator();
```

- `public GetPendingCount(System.String name) : System.Int32`  

```csharp
public System.Int32 GetPendingCount(System.String name);
```

- `private RunNextTask(System.String name) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RunNextTask(System.String name);
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```


## Nested types

- `Colossal.TaskManager+TaskQueue+<>c`  
- `Colossal.TaskManager+TaskQueue+<>c__DisplayClass10_0`  
- `Colossal.TaskManager+TaskQueue+<Enqueue>d__10`  
- `Colossal.TaskManager+TaskQueue+<RunNextTask>d__11`  

