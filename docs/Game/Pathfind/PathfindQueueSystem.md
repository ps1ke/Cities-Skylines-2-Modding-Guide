# Game.Pathfind.PathfindQueueSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Simulation.TransportLineSystem m_TransportLineSystem`  
- `private Game.Prefabs.NetInitializeSystem m_NetInitializeSystem`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction> m_CreateActions`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction> m_UpdateActions`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction> m_DeleteActions`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> m_PathfindActions`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> m_CoverageActions`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> m_AvailabilityActions`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction> m_DensityActions`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction> m_TimeActions`  
- `private Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction> m_FlowActions`  
- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_ActionTypes`  
- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_HighPriorityTypes`  
- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+ActionType> m_ModificationTypes`  
- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+WorkerActions> m_WorkerActions`  
- `private System.Collections.Generic.Queue<Game.Pathfind.PathfindQueueSystem+WorkerActions> m_WorkerActionPool`  
- `private System.Collections.Generic.List<Game.Pathfind.PathfindQueueSystem+WorkerData> m_WorkerData`  
- `private System.Collections.Generic.List<Game.Pathfind.PathfindQueueSystem+ThreadData> m_ThreadData`  
- `private System.Collections.Generic.List<Unity.Collections.AllocatorHelper<Colossal.Collections.UnsafeLinearAllocator>> m_AllocatorPool`  
- `private System.Int32 m_MaxThreadCount`  
- `private System.Int32 m_NextWorkerIndex`  
- `private System.Int32 m_LastWorkerIndex`  
- `private System.Int32 m_DependencyIndex`  
- `private System.Boolean m_RequireDebug`  
- `private static const System.Int32 WORKER_DATA_COUNT`  

## Constructors

- `public PathfindQueueSystem()`  

## Methods

- `public AddDataReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public Enqueue(Game.Pathfind.CreateAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public Enqueue(Game.Pathfind.UpdateAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public Enqueue(Game.Pathfind.DeleteAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority = False) : System.Void`  
- `public Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority = False) : System.Void`  
- `public Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority = False) : System.Void`  
- `public Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority = False) : System.Void`  
- `public Enqueue(Game.Pathfind.AvailabilityAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system) : System.Void`  
- `public Enqueue(Game.Pathfind.DensityAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public Enqueue(Game.Pathfind.TimeAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public Enqueue(Game.Pathfind.FlowAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  
- `private Enqueue<T>(T action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, Game.Pathfind.PathfindQueueSystem+ActionList<T> list, Game.Pathfind.PathfindQueueSystem+ActionType type, System.Object system, System.Boolean highPriority, System.Boolean modification) : System.Void`  
- `private Enqueue<T>(T action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, Game.Pathfind.PathfindQueueSystem+ActionList<T> list, Game.Pathfind.PathfindQueueSystem+ActionType type, System.Object system, System.Boolean highPriority, Game.Pathfind.PathEventData eventData) : System.Void`  
- `public GetAvailabilityActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction>`  
- `public GetCoverageActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction>`  
- `public GetCreateActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction>`  
- `public GetDataContainer(Unity.Jobs.JobHandle& dependencies) : Game.Pathfind.NativePathfindData`  
- `public GetDeleteActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction>`  
- `public GetDensityActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction>`  
- `public GetFlowActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction>`  
- `public GetGraphMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory) : System.Void`  
- `public GetGraphSize() : System.Int32`  
- `public GetPathfindActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction>`  
- `public GetQueryMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory) : System.Void`  
- `public GetTimeActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction>`  
- `public GetUpdateActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public RequireDebug() : System.Void`  
- `private RequireWorkerActions(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions) : System.Void`  
- `private ScheduleModificationJob<T>(T job) : Unity.Jobs.JobHandle`  
- `private ScheduleWorkerJobs(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions) : System.Void`  

## Nested types

- `Game.Pathfind.PathfindQueueSystem+ActionListItem<T>`  
- `Game.Pathfind.PathfindQueueSystem+ActionList<T>`  
- `Game.Pathfind.PathfindQueueSystem+ActionType`  
- `Game.Pathfind.PathfindQueueSystem+WorkerData`  
- `Game.Pathfind.PathfindQueueSystem+WorkerActions`  
- `Game.Pathfind.PathfindQueueSystem+ThreadData`  
- `Game.Pathfind.PathfindQueueSystem+WorkerAction`  
- `Game.Pathfind.PathfindQueueSystem+PathfindWorkerJob`  

