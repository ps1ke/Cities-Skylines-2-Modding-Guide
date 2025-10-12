# Colossal.TaskManager+TaskCompletionSources

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>>>`, `System.Collections.IEnumerable`  

## Fields

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>> m_TaskCompletions`  

## Properties

- `public System.Int32 Count { get }`  

## Constructors

- `public TaskCompletionSources()`  

## Methods

- `public Add(System.String id, System.Action action) : System.Threading.Tasks.Task<System.Boolean>`  
- `public Complete(System.String id, System.Boolean result) : System.Void`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, System.Threading.Tasks.TaskCompletionSource<System.Boolean>>>`  
- `public IsWaiting(System.String id) : System.Boolean`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `private WaitForCompletion(System.String id, System.Threading.Tasks.Task task, System.Action action) : System.Void`  

## Nested types

- `Colossal.TaskManager+TaskCompletionSources+<WaitForCompletion>d__3`  

