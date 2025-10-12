# Colossal.TaskManager+TaskQueue

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<System.String>`, `System.Collections.IEnumerable`  

## Fields

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Collections.Concurrent.ConcurrentQueue<System.Func<System.Threading.Tasks.Task>>> m_TaskQueues`  
- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>> m_CompletionSources`  
- `private readonly System.Collections.Concurrent.ConcurrentBag<System.String> m_RunningTasks`  
- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_CompletionSource`  

## Properties

- `public System.Int32 count { get }`  

## Constructors

- `public TaskQueue()`  

## Methods

- `public Complete(System.String name) : System.Threading.Tasks.Task`  
- `public Complete() : System.Threading.Tasks.Task`  
- `public Enqueue(System.String name, System.Func<System.Threading.Tasks.Task> taskFunc, System.Int32 cap = 0) : System.Threading.Tasks.Task`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<System.String>`  
- `public GetPendingCount(System.String name) : System.Int32`  
- `private RunNextTask(System.String name) : System.Threading.Tasks.Task`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

## Nested types

- `Colossal.TaskManager+TaskQueue+<>c`  
- `Colossal.TaskManager+TaskQueue+<>c__DisplayClass10_0`  
- `Colossal.TaskManager+TaskQueue+<Enqueue>d__10`  
- `Colossal.TaskManager+TaskQueue+<RunNextTask>d__11`  

