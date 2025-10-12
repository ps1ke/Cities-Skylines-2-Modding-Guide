# Colossal.TaskManager

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.OnNotifyProgress onNotifyProgress`  
- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, Colossal.ProgressTracker> m_TaskProgress`  
- `private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.ProgressTracker+Group, System.Int32> m_TaskGroups`  
- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.String, System.Threading.Tasks.Task> m_TaskRegistry`  
- `private readonly Colossal.TaskManager+TaskQueue m_TaskQueue`  
- `private readonly Colossal.TaskManager+TaskCompletionSources <taskCompletionSources>k__BackingField`  
- `private readonly Colossal.TaskProgress <progress>k__BackingField`  
- `private static Colossal.TaskManager s_Instance`  
- `private static Colossal.Logging.ILog log`  

## Properties

- `public static Colossal.TaskManager instance { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.ProgressTracker> taskProgress { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<Colossal.ProgressTracker+Group, System.Int32> taskGroups { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Threading.Tasks.Task> taskRegistry { get }`  
- `public Colossal.TaskManager+TaskQueue taskQueue { get }`  
- `public Colossal.TaskManager+TaskCompletionSources taskCompletionSources { get }`  
- `public Colossal.TaskProgress progress { get }`  

## Constructors

- `public TaskManager()`  

## Methods

- `private <.ctor>b__28_0(Colossal.ProgressTracker info) : System.Void`  
- `public Clear() : System.Threading.Tasks.Task`  
- `public Complete(System.String name) : System.Threading.Tasks.Task`  
- `public CompleteAndClear() : System.Threading.Tasks.Task`  
- `public EnqueueTask(System.String name, System.Func<System.Threading.Tasks.Task> task, System.Int32 cap = 0) : System.Threading.Tasks.Task`  
- `public GetTaskProgress(Colossal.ProgressTracker+Group group) : System.Single`  
- `public GetTaskProgress(System.String taskName) : System.Single`  
- `public Prune() : System.Void`  
- `public ScheduleGroup(Colossal.ProgressTracker+Group group, System.Int32 count) : System.Void`  
- `public SharedTask(System.String name, System.Func<System.Threading.Tasks.Task> func) : System.Threading.Tasks.Task`  
- `public SharedTask(System.String name, System.Func<System.Threading.CancellationToken, System.Threading.Tasks.Task> func, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public SharedTask<T>(System.String name, System.Func<T, System.Threading.CancellationToken, System.Threading.Tasks.Task> func, T arg, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public SharedTask<T1, T2>(System.String name, System.Func<T1, T2, System.Threading.CancellationToken, System.Threading.Tasks.Task> func, T1 arg1, T2 arg2, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public TrackedTask<T>(System.String name, T task) : T`  
- `public TryGetTaskProgress(System.String taskName, System.Single& progress) : System.Boolean`  

## Events

- `onNotifyProgress` : `Colossal.OnNotifyProgress`  

## Nested types

- `Colossal.TaskManager+TaskCompletionSources`  
- `Colossal.TaskManager+TaskQueue`  
- `Colossal.TaskManager+<>c`  
- `Colossal.TaskManager+<>c__DisplayClass35_0`  
- `Colossal.TaskManager+<>c__DisplayClass41_0`  
- `Colossal.TaskManager+<CompleteAndClear>d__39`  

