# Colossal.TaskManager+TaskCompletionSources

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>>>`, `System.Collections.IEnumerable`  

## Code

```csharp
public class TaskCompletionSources : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>>>, System.Collections.IEnumerable
{
    private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>> m_TaskCompletions;

    public System.Int32 Count { get; }

    public TaskCompletionSources();

    public System.Threading.Tasks.Task<System.Boolean> Add(System.String id, System.Action action);
    public System.Void Complete(System.String id, System.Boolean result);
    public System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>>> GetEnumerator();
    public System.Boolean IsWaiting(System.String id);
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    private System.Void WaitForCompletion(System.String id, System.Threading.Tasks.Task task, System.Action action);
}
```


## Fields

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>> m_TaskCompletions`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>> m_TaskCompletions;
```


## Properties

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```


## Constructors

- `public TaskCompletionSources()`  

```csharp
public TaskCompletionSources();
```


## Methods

- `public Add(System.String id, System.Action action) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Add(System.String id, System.Action action);
```

- `public Complete(System.String id, System.Boolean result) : System.Void`  

```csharp
public System.Void Complete(System.String id, System.Boolean result);
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>>>`  

```csharp
public System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>>> GetEnumerator();
```

- `public IsWaiting(System.String id) : System.Boolean`  

```csharp
public System.Boolean IsWaiting(System.String id);
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `private WaitForCompletion(System.String id, System.Threading.Tasks.Task task, System.Action action) : System.Void`  

```csharp
private System.Void WaitForCompletion(System.String id, System.Threading.Tasks.Task task, System.Action action);
```


## Nested types

- `Colossal.TaskManager+TaskCompletionSources+<WaitForCompletion>d__3`  

