# Colossal.AssetPipeline.MainThreadDispatcher

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.MainThreadDispatcher+Task> m_DispatchQueue`  
- `private System.Threading.ManualResetEvent m_DataEvent`  

## Properties

- `public System.Int32 pendingTasksCount { get }`  
- `public System.Boolean hasPendingTasks { get }`  

## Constructors

- `public MainThreadDispatcher()`  

## Methods

- `private AddTask(Colossal.AssetPipeline.MainThreadDispatcher+Task task) : System.Void`  
- `public Dispatch(System.Action action) : Colossal.AssetPipeline.MainThreadDispatcher+Task`  
- `public Dispatch<T>(System.Func<T> func) : Colossal.AssetPipeline.MainThreadDispatcher+Task<T>`  
- `public ProcessTasks() : System.Void`  

## Nested types

- `Colossal.AssetPipeline.MainThreadDispatcher+Task`  
- `Colossal.AssetPipeline.MainThreadDispatcher+Task<T>`  

