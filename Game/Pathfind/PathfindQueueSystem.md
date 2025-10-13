# Game.Pathfind.PathfindQueueSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathfindQueueSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.TransportLineSystem m_TransportLineSystem;
    private Game.Prefabs.NetInitializeSystem m_NetInitializeSystem;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction> m_CreateActions;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction> m_UpdateActions;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction> m_DeleteActions;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> m_PathfindActions;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> m_CoverageActions;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> m_AvailabilityActions;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction> m_DensityActions;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction> m_TimeActions;
    private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction> m_FlowActions;
    private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_ActionTypes;
    private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_HighPriorityTypes;
    private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_ModificationTypes;
    private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+WorkerActions> m_WorkerActions;
    private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+WorkerActions> m_WorkerActionPool;
    private System.Collections.Generic.List<Game.Pathfind.PathfindQueueSystem+WorkerData> m_WorkerData;
    private System.Collections.Generic.List<Game.Pathfind.PathfindQueueSystem+ThreadData> m_ThreadData;
    private System.Collections.Generic.List<Unity.Collections.AllocatorHelper<Colossal.Collections.UnsafeLinearAllocator>> m_AllocatorPool;
    private System.Int32 m_MaxThreadCount;
    private System.Int32 m_NextWorkerIndex;
    private System.Int32 m_LastWorkerIndex;
    private System.Int32 m_DependencyIndex;
    private System.Boolean m_RequireDebug;
    private static const System.Int32 WORKER_DATA_COUNT;

    public PathfindQueueSystem();

    public System.Void AddDataReader(Unity.Jobs.JobHandle handle);
    public System.Void Enqueue(Game.Pathfind.CreateAction action, Unity.Jobs.JobHandle dependencies);
    public System.Void Enqueue(Game.Pathfind.UpdateAction action, Unity.Jobs.JobHandle dependencies);
    public System.Void Enqueue(Game.Pathfind.DeleteAction action, Unity.Jobs.JobHandle dependencies);
    public System.Void Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority);
    public System.Void Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority);
    public System.Void Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority);
    public System.Void Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority);
    public System.Void Enqueue(Game.Pathfind.AvailabilityAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system);
    public System.Void Enqueue(Game.Pathfind.DensityAction action, Unity.Jobs.JobHandle dependencies);
    public System.Void Enqueue(Game.Pathfind.TimeAction action, Unity.Jobs.JobHandle dependencies);
    public System.Void Enqueue(Game.Pathfind.FlowAction action, Unity.Jobs.JobHandle dependencies);
    private System.Void Enqueue<T>(T action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, Game.Pathfind.PathfindQueueSystem+ActionList<T> list, Game.Pathfind.PathfindQueueSystem+ActionType type, System.Object system, System.Boolean highPriority, System.Boolean modification);
    private System.Void Enqueue<T>(T action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, Game.Pathfind.PathfindQueueSystem+ActionList<T> list, Game.Pathfind.PathfindQueueSystem+ActionType type, System.Object system, System.Boolean highPriority, Game.Pathfind.PathEventData eventData);
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> GetAvailabilityActions();
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> GetCoverageActions();
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction> GetCreateActions();
    public Game.Pathfind.NativePathfindData GetDataContainer(Unity.Jobs.JobHandle& dependencies);
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction> GetDeleteActions();
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction> GetDensityActions();
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction> GetFlowActions();
    public System.Void GetGraphMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory);
    public System.Int32 GetGraphSize();
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> GetPathfindActions();
    public System.Void GetQueryMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory);
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction> GetTimeActions();
    public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction> GetUpdateActions();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void RequireDebug();
    private System.Void RequireWorkerActions(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions);
    private Unity.Jobs.JobHandle ScheduleModificationJob<T>(T job);
    private System.Void ScheduleWorkerJobs(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions);
}
```


## Fields

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.TransportLineSystem m_TransportLineSystem`  

```csharp
private Game.Simulation.TransportLineSystem m_TransportLineSystem;
```

- `private Game.Prefabs.NetInitializeSystem m_NetInitializeSystem`  

```csharp
private Game.Prefabs.NetInitializeSystem m_NetInitializeSystem;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction> m_CreateActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction> m_CreateActions;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction> m_UpdateActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction> m_UpdateActions;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction> m_DeleteActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction> m_DeleteActions;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> m_PathfindActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> m_PathfindActions;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> m_CoverageActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> m_CoverageActions;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> m_AvailabilityActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> m_AvailabilityActions;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction> m_DensityActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction> m_DensityActions;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction> m_TimeActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction> m_TimeActions;
```

- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction> m_FlowActions`  

```csharp
private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction> m_FlowActions;
```

- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_ActionTypes`  

```csharp
private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_ActionTypes;
```

- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_HighPriorityTypes`  

```csharp
private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_HighPriorityTypes;
```

- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_ModificationTypes`  

```csharp
private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_ModificationTypes;
```

- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+WorkerActions> m_WorkerActions`  

```csharp
private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+WorkerActions> m_WorkerActions;
```

- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+WorkerActions> m_WorkerActionPool`  

```csharp
private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+WorkerActions> m_WorkerActionPool;
```

- `private System.Collections.Generic.List<Game.Pathfind.PathfindQueueSystem+WorkerData> m_WorkerData`  

```csharp
private System.Collections.Generic.List<Game.Pathfind.PathfindQueueSystem+WorkerData> m_WorkerData;
```

- `private System.Collections.Generic.List<Game.Pathfind.PathfindQueueSystem+ThreadData> m_ThreadData`  

```csharp
private System.Collections.Generic.List<Game.Pathfind.PathfindQueueSystem+ThreadData> m_ThreadData;
```

- `private System.Collections.Generic.List<Unity.Collections.AllocatorHelper<Colossal.Collections.UnsafeLinearAllocator>> m_AllocatorPool`  

```csharp
private System.Collections.Generic.List<Unity.Collections.AllocatorHelper<Colossal.Collections.UnsafeLinearAllocator>> m_AllocatorPool;
```

- `private System.Int32 m_MaxThreadCount`  

```csharp
private System.Int32 m_MaxThreadCount;
```

- `private System.Int32 m_NextWorkerIndex`  

```csharp
private System.Int32 m_NextWorkerIndex;
```

- `private System.Int32 m_LastWorkerIndex`  

```csharp
private System.Int32 m_LastWorkerIndex;
```

- `private System.Int32 m_DependencyIndex`  

```csharp
private System.Int32 m_DependencyIndex;
```

- `private System.Boolean m_RequireDebug`  

```csharp
private System.Boolean m_RequireDebug;
```

- `private static const System.Int32 WORKER_DATA_COUNT`  

```csharp
private static const System.Int32 WORKER_DATA_COUNT;
```


## Constructors

- `public PathfindQueueSystem()`  

```csharp
public PathfindQueueSystem();
```


## Methods

- `public AddDataReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddDataReader(Unity.Jobs.JobHandle handle);
```

- `public Enqueue(Game.Pathfind.CreateAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.CreateAction action, Unity.Jobs.JobHandle dependencies);
```

- `public Enqueue(Game.Pathfind.UpdateAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.UpdateAction action, Unity.Jobs.JobHandle dependencies);
```

- `public Enqueue(Game.Pathfind.DeleteAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.DeleteAction action, Unity.Jobs.JobHandle dependencies);
```

- `public Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority = False) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority);
```

- `public Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority = False) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority);
```

- `public Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority = False) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority);
```

- `public Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority = False) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority);
```

- `public Enqueue(Game.Pathfind.AvailabilityAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.AvailabilityAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system);
```

- `public Enqueue(Game.Pathfind.DensityAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.DensityAction action, Unity.Jobs.JobHandle dependencies);
```

- `public Enqueue(Game.Pathfind.TimeAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.TimeAction action, Unity.Jobs.JobHandle dependencies);
```

- `public Enqueue(Game.Pathfind.FlowAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void Enqueue(Game.Pathfind.FlowAction action, Unity.Jobs.JobHandle dependencies);
```

- `private Enqueue<T>(T action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, Game.Pathfind.PathfindQueueSystem+ActionList<T> list, Game.Pathfind.PathfindQueueSystem+ActionType type, System.Object system, System.Boolean highPriority, System.Boolean modification) : System.Void`  

```csharp
private System.Void Enqueue<T>(T action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, Game.Pathfind.PathfindQueueSystem+ActionList<T> list, Game.Pathfind.PathfindQueueSystem+ActionType type, System.Object system, System.Boolean highPriority, System.Boolean modification);
```

- `private Enqueue<T>(T action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, Game.Pathfind.PathfindQueueSystem+ActionList<T> list, Game.Pathfind.PathfindQueueSystem+ActionType type, System.Object system, System.Boolean highPriority, Game.Pathfind.PathEventData eventData) : System.Void`  

```csharp
private System.Void Enqueue<T>(T action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, Game.Pathfind.PathfindQueueSystem+ActionList<T> list, Game.Pathfind.PathfindQueueSystem+ActionType type, System.Object system, System.Boolean highPriority, Game.Pathfind.PathEventData eventData);
```

- `public GetAvailabilityActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> GetAvailabilityActions();
```

- `public GetCoverageActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> GetCoverageActions();
```

- `public GetCreateActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction> GetCreateActions();
```

- `public GetDataContainer(Unity.Jobs.JobHandle& dependencies) : Game.Pathfind.NativePathfindData`  

```csharp
public Game.Pathfind.NativePathfindData GetDataContainer(Unity.Jobs.JobHandle& dependencies);
```

- `public GetDeleteActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction> GetDeleteActions();
```

- `public GetDensityActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction> GetDensityActions();
```

- `public GetFlowActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction> GetFlowActions();
```

- `public GetGraphMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory) : System.Void`  

```csharp
public System.Void GetGraphMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory);
```

- `public GetGraphSize() : System.Int32`  

```csharp
public System.Int32 GetGraphSize();
```

- `public GetPathfindActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> GetPathfindActions();
```

- `public GetQueryMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory) : System.Void`  

```csharp
public System.Void GetQueryMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory);
```

- `public GetTimeActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction> GetTimeActions();
```

- `public GetUpdateActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction>`  

```csharp
public Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction> GetUpdateActions();
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

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public RequireDebug() : System.Void`  

```csharp
public System.Void RequireDebug();
```

- `private RequireWorkerActions(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions) : System.Void`  

```csharp
private System.Void RequireWorkerActions(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions);
```

- `private ScheduleModificationJob<T>(T job) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle ScheduleModificationJob<T>(T job);
```

- `private ScheduleWorkerJobs(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions) : System.Void`  

```csharp
private System.Void ScheduleWorkerJobs(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions);
```


## Nested types

- `Game.Pathfind.PathfindQueueSystem+ActionListItem<T>`  
- `Game.Pathfind.PathfindQueueSystem+ActionList<T>`  
- `Game.Pathfind.PathfindQueueSystem+ActionType`  
- `Game.Pathfind.PathfindQueueSystem+WorkerData`  
- `Game.Pathfind.PathfindQueueSystem+WorkerActions`  
- `Game.Pathfind.PathfindQueueSystem+ThreadData`  
- `Game.Pathfind.PathfindQueueSystem+WorkerAction`  
- `Game.Pathfind.PathfindQueueSystem+PathfindWorkerJob`  

