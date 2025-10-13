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
[Preserve]
	public PathfindQueueSystem()
	{
	}
```


## Methods

- `public AddDataReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddDataReader(JobHandle handle)
	{
		WorkerData workerData = m_WorkerData[m_NextWorkerIndex];
		workerData.m_ReadHandle = JobHandle.CombineDependencies(workerData.m_ReadHandle, handle);
	}
```

- `public Enqueue(Game.Pathfind.CreateAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.UpdateAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.DeleteAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority = False) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.PathfindAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority = False) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, System.Boolean highPriority = False) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.CoverageAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system, Game.Pathfind.PathEventData eventData, System.Boolean highPriority = False) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.AvailabilityAction action, Unity.Entities.Entity owner, Unity.Jobs.JobHandle dependencies, System.UInt32 resultFrame, System.Object system) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.DensityAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.TimeAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
```

- `public Enqueue(Game.Pathfind.FlowAction action, Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void Enqueue(FlowAction action, JobHandle dependencies)
	{
		Enqueue(action, Entity.Null, dependencies, uint.MaxValue, m_FlowActions, ActionType.Flow, null, highPriority: false, modification: true);
	}
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
public ActionList<AvailabilityAction> GetAvailabilityActions()
	{
		return m_AvailabilityActions;
	}
```

- `public GetCoverageActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction>`  

```csharp
public ActionList<CoverageAction> GetCoverageActions()
	{
		return m_CoverageActions;
	}
```

- `public GetCreateActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CreateAction>`  

```csharp
public ActionList<CreateAction> GetCreateActions()
	{
		return m_CreateActions;
	}
```

- `public GetDataContainer(Unity.Jobs.JobHandle& dependencies) : Game.Pathfind.NativePathfindData`  

```csharp
public NativePathfindData GetDataContainer(out JobHandle dependencies)
	{
		WorkerData workerData = m_WorkerData[m_NextWorkerIndex];
		dependencies = workerData.m_WriteHandle;
		return workerData.m_PathfindData;
	}
```

- `public GetDeleteActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DeleteAction>`  

```csharp
public ActionList<DeleteAction> GetDeleteActions()
	{
		return m_DeleteActions;
	}
```

- `public GetDensityActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.DensityAction>`  

```csharp
public ActionList<DensityAction> GetDensityActions()
	{
		return m_DensityActions;
	}
```

- `public GetFlowActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.FlowAction>`  

```csharp
public ActionList<FlowAction> GetFlowActions()
	{
		return m_FlowActions;
	}
```

- `public GetGraphMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory) : System.Void`  

```csharp
public void GetGraphMemory(out uint usedMemory, out uint allocatedMemory)
	{
		usedMemory = 0u;
		allocatedMemory = 0u;
		for (int i = 0; i < m_WorkerData.Count; i++)
		{
			m_WorkerData[i].m_PathfindData.GetMemoryStats(out var used, out var allocated);
			usedMemory += used;
			allocatedMemory += allocated;
		}
	}
```

- `public GetGraphSize() : System.Int32`  

```csharp
public int GetGraphSize()
	{
		return m_WorkerData[m_NextWorkerIndex].m_PathfindData.Size;
	}
```

- `public GetPathfindActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction>`  

```csharp
public ActionList<PathfindAction> GetPathfindActions()
	{
		return m_PathfindActions;
	}
```

- `public GetQueryMemory(System.UInt32& usedMemory, System.UInt32& allocatedMemory) : System.Void`  

```csharp
public void GetQueryMemory(out uint usedMemory, out uint allocatedMemory)
	{
		usedMemory = 0u;
		allocatedMemory = 0u;
		for (int i = 0; i < m_ThreadData.Count; i++)
		{
			ref UnsafeLinearAllocator allocator = ref m_ThreadData[i].m_Allocator.Allocator;
			usedMemory += allocator.Used;
			allocatedMemory += allocator.Size;
		}
		for (int j = 0; j < m_AllocatorPool.Count; j++)
		{
			ref UnsafeLinearAllocator allocator2 = ref m_AllocatorPool[j].Allocator;
			usedMemory += allocator2.Used;
			allocatedMemory += allocator2.Size;
		}
	}
```

- `public GetTimeActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.TimeAction>`  

```csharp
public ActionList<TimeAction> GetTimeActions()
	{
		return m_TimeActions;
	}
```

- `public GetUpdateActions() : Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.UpdateAction>`  

```csharp
public ActionList<UpdateAction> GetUpdateActions()
	{
		return m_UpdateActions;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_TransportLineSystem = base.World.GetOrCreateSystemManaged<TransportLineSystem>();
		m_NetInitializeSystem = base.World.GetOrCreateSystemManaged<NetInitializeSystem>();
		m_MaxThreadCount = math.max(1, JobsUtility.JobWorkerCount / 2);
		m_CreateActions = new ActionList<CreateAction>();
		m_UpdateActions = new ActionList<UpdateAction>();
		m_DeleteActions = new ActionList<DeleteAction>();
		m_PathfindActions = new ActionList<PathfindAction>();
		m_CoverageActions = new ActionList<CoverageAction>();
		m_AvailabilityActions = new ActionList<AvailabilityAction>();
		m_DensityActions = new ActionList<DensityAction>();
		m_TimeActions = new ActionList<TimeAction>();
		m_FlowActions = new ActionList<FlowAction>();
		m_ActionTypes = new Queue<ActionType>();
		m_HighPriorityTypes = new Queue<ActionType>();
		m_ModificationTypes = new Queue<ActionType>();
		m_WorkerActions = new Queue<WorkerActions>();
		m_WorkerActionPool = new Queue<WorkerActions>();
		m_WorkerData = new List<WorkerData>(2);
		for (int i = 0; i < 2; i++)
		{
			m_WorkerData.Add(new WorkerData(Allocator.Persistent));
		}
		m_ThreadData = new List<ThreadData>(m_MaxThreadCount);
		m_AllocatorPool = new List<AllocatorHelper<UnsafeLinearAllocator>>(m_MaxThreadCount);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		for (int i = 0; i < m_ThreadData.Count; i++)
		{
			ThreadData threadData = m_ThreadData[i];
			threadData.m_JobHandle.Complete();
			UnsafeLinearAllocator allocator = threadData.m_Allocator.Allocator;
			threadData.m_Allocator.Dispose();
			allocator.Dispose();
		}
		for (int j = 0; j < m_AllocatorPool.Count; j++)
		{
			UnsafeLinearAllocator allocator2 = m_AllocatorPool[j].Allocator;
			m_AllocatorPool[j].Dispose();
			allocator2.Dispose();
		}
		m_CreateActions.Dispose();
		m_UpdateActions.Dispose();
		m_DeleteActions.Dispose();
		m_PathfindActions.Dispose();
		m_CoverageActions.Dispose();
		m_AvailabilityActions.Dispose();
		m_DensityActions.Dispose();
		m_TimeActions.Dispose();
		m_FlowActions.Dispose();
		WorkerActions result;
		while (m_WorkerActions.TryDequeue(out result))
		{
			result.Dispose();
		}
		WorkerActions result2;
		while (m_WorkerActionPool.TryDequeue(out result2))
		{
			result2.Dispose();
		}
		for (int k = 0; k < m_WorkerData.Count; k++)
		{
			m_WorkerData[k].Dispose();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = m_RequireDebug;
		m_RequireDebug = false;
		for (int i = 0; i < m_AllocatorPool.Count; i++)
		{
			m_AllocatorPool[i].Allocator.Rewind(updateSize: true);
		}
		int num = 0;
		for (int j = 0; j < m_ThreadData.Count; j++)
		{
			ThreadData value = m_ThreadData[j];
			if (value.m_JobHandle.IsCompleted)
			{
				value.m_JobHandle.Complete();
				m_AllocatorPool.Add(value.m_Allocator);
				if (num < m_DependencyIndex)
				{
					m_DependencyIndex--;
				}
			}
			else
			{
				m_ThreadData[num++] = value;
			}
		}
		if (num < m_ThreadData.Count)
		{
			m_ThreadData.RemoveRange(num, m_ThreadData.Count - num);
		}
		for (int k = 0; k < m_WorkerData.Count; k++)
		{
			WorkerData workerData = m_WorkerData[k];
			if (workerData.m_WriteHandle.IsCompleted)
			{
				workerData.m_WriteHandle.Complete();
			}
			if (workerData.m_ReadHandle.IsCompleted)
			{
				workerData.m_ReadHandle.Complete();
			}
		}
		WorkerActions result;
		while (m_WorkerActions.TryPeek(out result) && result.m_ReadHandle.IsCompleted)
		{
			result.Clear();
			m_WorkerActions.Dequeue();
			m_WorkerActionPool.Enqueue(result);
		}
		m_PathfindSetupSystem.CompleteSetup();
		WorkerActions currentActions = null;
		try
		{
			while (true)
			{
				ActionType actionType;
				bool flag2;
				bool flag3;
				if (m_HighPriorityTypes.Count != 0)
				{
					actionType = m_HighPriorityTypes.Peek();
					flag2 = true;
					flag3 = false;
				}
				else if (m_ModificationTypes.Count != 0)
				{
					actionType = m_ModificationTypes.Peek();
					flag2 = false;
					flag3 = true;
				}
				else
				{
					if (m_ActionTypes.Count == 0)
					{
						break;
					}
					actionType = m_ActionTypes.Peek();
					flag2 = false;
					flag3 = false;
				}
				switch (actionType)
				{
				case ActionType.Create:
				{
					ActionListItem<CreateAction> value5 = m_CreateActions.m_Items[m_CreateActions.m_NextIndex];
					if (!value5.m_Dependencies.IsCompleted)
					{
						return;
					}
					value5.m_Dependencies.Complete();
					ScheduleWorkerJobs(ref currentActions);
					value5.m_Dependencies = ScheduleModificationJob(new ModificationJobs.CreateEdgesJob
					{
						m_Action = value5.m_Action
					});
					value5.m_Flags = (value5.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_CreateActions.m_Items[m_CreateActions.m_NextIndex++] = value5;
					break;
				}
				case ActionType.Update:
				{
					ActionListItem<UpdateAction> value10 = m_UpdateActions.m_Items[m_UpdateActions.m_NextIndex];
					if (!value10.m_Dependencies.IsCompleted)
					{
						return;
					}
					value10.m_Dependencies.Complete();
					ScheduleWorkerJobs(ref currentActions);
					value10.m_Dependencies = ScheduleModificationJob(new ModificationJobs.UpdateEdgesJob
					{
						m_Action = value10.m_Action
					});
					value10.m_Flags = (value10.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_UpdateActions.m_Items[m_UpdateActions.m_NextIndex++] = value10;
					break;
				}
				case ActionType.Delete:
				{
					ActionListItem<DeleteAction> value7 = m_DeleteActions.m_Items[m_DeleteActions.m_NextIndex];
					if (!value7.m_Dependencies.IsCompleted)
					{
						return;
					}
					value7.m_Dependencies.Complete();
					ScheduleWorkerJobs(ref currentActions);
					value7.m_Dependencies = ScheduleModificationJob(new ModificationJobs.DeleteEdgesJob
					{
						m_Action = value7.m_Action
					});
					value7.m_Flags = (value7.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_DeleteActions.m_Items[m_DeleteActions.m_NextIndex++] = value7;
					break;
				}
				case ActionType.Pathfind:
				{
					ActionListItem<PathfindAction> value9 = m_PathfindActions.m_Items[m_PathfindActions.m_NextIndex];
					if (!value9.m_Dependencies.IsCompleted || (flag && (value9.m_Flags & PathFlags.Debug) == 0))
					{
						return;
					}
					value9.m_Dependencies.Complete();
					RequireWorkerActions(ref currentActions);
					currentActions.Add(actionType, flag2, ref value9.m_Action.data);
					value9.m_Flags = (value9.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_PathfindActions.m_Items[m_PathfindActions.m_NextIndex++] = value9;
					if (flag2)
					{
						m_PathfindActions.m_PriorityCount--;
					}
					break;
				}
				case ActionType.Coverage:
				{
					ActionListItem<CoverageAction> value3 = m_CoverageActions.m_Items[m_CoverageActions.m_NextIndex];
					if (!value3.m_Dependencies.IsCompleted)
					{
						return;
					}
					value3.m_Dependencies.Complete();
					RequireWorkerActions(ref currentActions);
					currentActions.Add(actionType, flag2, ref value3.m_Action.data);
					value3.m_Flags = (value3.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_CoverageActions.m_Items[m_CoverageActions.m_NextIndex++] = value3;
					if (flag2)
					{
						m_CoverageActions.m_PriorityCount--;
					}
					break;
				}
				case ActionType.Availability:
				{
					ActionListItem<AvailabilityAction> value8 = m_AvailabilityActions.m_Items[m_AvailabilityActions.m_NextIndex];
					if (!value8.m_Dependencies.IsCompleted)
					{
						return;
					}
					value8.m_Dependencies.Complete();
					RequireWorkerActions(ref currentActions);
					currentActions.Add(actionType, flag2, ref value8.m_Action.data);
					value8.m_Flags = (value8.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_AvailabilityActions.m_Items[m_AvailabilityActions.m_NextIndex++] = value8;
					if (flag2)
					{
						m_CoverageActions.m_PriorityCount--;
					}
					break;
				}
				case ActionType.Density:
				{
					ActionListItem<DensityAction> value6 = m_DensityActions.m_Items[m_DensityActions.m_NextIndex];
					if (!value6.m_Dependencies.IsCompleted)
					{
						return;
					}
					value6.m_Dependencies.Complete();
					ScheduleWorkerJobs(ref currentActions);
					value6.m_Dependencies = ScheduleModificationJob(new ModificationJobs.SetDensityJob
					{
						m_Action = value6.m_Action
					});
					value6.m_Flags = (value6.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_DensityActions.m_Items[m_DensityActions.m_NextIndex++] = value6;
					break;
				}
				case ActionType.Time:
				{
					ActionListItem<TimeAction> value4 = m_TimeActions.m_Items[m_TimeActions.m_NextIndex];
					if (!value4.m_Dependencies.IsCompleted)
					{
						return;
					}
					value4.m_Dependencies.Complete();
					ScheduleWorkerJobs(ref currentActions);
					value4.m_Dependencies = ScheduleModificationJob(new ModificationJobs.SetTimeJob
					{
						m_Action = value4.m_Action
					});
					value4.m_Flags = (value4.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_TimeActions.m_Items[m_TimeActions.m_NextIndex++] = value4;
					break;
				}
				case ActionType.Flow:
				{
					ActionListItem<FlowAction> value2 = m_FlowActions.m_Items[m_FlowActions.m_NextIndex];
					if (!value2.m_Dependencies.IsCompleted)
					{
						return;
					}
					value2.m_Dependencies.Complete();
					ScheduleWorkerJobs(ref currentActions);
					value2.m_Dependencies = ScheduleModificationJob(new ModificationJobs.SetFlowJob
					{
						m_Action = value2.m_Action
					});
					value2.m_Flags = (value2.m_Flags & ~PathFlags.Pending) | PathFlags.Scheduled;
					m_FlowActions.m_Items[m_FlowActions.m_NextIndex++] = value2;
					break;
				}
				}
				if (flag2)
				{
					m_HighPriorityTypes.Dequeue();
				}
				else if (flag3)
				{
					m_ModificationTypes.Dequeue();
				}
				else
				{
					m_ActionTypes.Dequeue();
				}
			}
		}
		finally
		{
			ScheduleWorkerJobs(ref currentActions);
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		for (int i = 0; i < m_ThreadData.Count; i++)
		{
			ThreadData threadData = m_ThreadData[i];
			threadData.m_JobHandle.Complete();
			m_AllocatorPool.Add(threadData.m_Allocator);
		}
		m_ThreadData.Clear();
		m_DependencyIndex = 0;
		m_CreateActions.Clear();
		m_UpdateActions.Clear();
		m_DeleteActions.Clear();
		m_PathfindActions.Clear();
		m_CoverageActions.Clear();
		m_AvailabilityActions.Clear();
		m_DensityActions.Clear();
		m_TimeActions.Clear();
		m_FlowActions.Clear();
		m_ActionTypes.Clear();
		m_HighPriorityTypes.Clear();
		m_ModificationTypes.Clear();
		WorkerActions result;
		while (m_WorkerActions.TryDequeue(out result))
		{
			result.Clear();
			m_WorkerActionPool.Enqueue(result);
		}
		for (int j = 0; j < m_WorkerData.Count; j++)
		{
			m_WorkerData[j].Clear();
		}
	}
```

- `public RequireDebug() : System.Void`  

```csharp
public void RequireDebug()
	{
		m_RequireDebug = true;
	}
```

- `private RequireWorkerActions(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions) : System.Void`  

```csharp
private void RequireWorkerActions(ref WorkerActions currentActions)
	{
		if (currentActions == null)
		{
			if (!m_WorkerActionPool.TryDequeue(out currentActions))
			{
				currentActions = new WorkerActions(Allocator.Persistent);
			}
			m_WorkerActions.Enqueue(currentActions);
		}
	}
```

- `private ScheduleModificationJob<T>(T job) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle ScheduleModificationJob<T>(T job);
```

- `private ScheduleWorkerJobs(Game.Pathfind.PathfindQueueSystem+WorkerActions& currentActions) : System.Void`  

```csharp
private void ScheduleWorkerJobs(ref WorkerActions currentActions)
	{
		if (currentActions == null)
		{
			return;
		}
		WorkerData workerData = m_WorkerData[m_NextWorkerIndex];
		int num = math.min(currentActions.m_Actions.Length, math.max(m_MaxThreadCount, currentActions.m_HighPriorityCount));
		int num2 = m_MaxThreadCount + currentActions.m_HighPriorityCount;
		int count = m_ThreadData.Count;
		PathfindWorkerJob jobData = new PathfindWorkerJob
		{
			m_RandomSeed = RandomSeed.Next(),
			m_PathfindData = workerData.m_PathfindData,
			m_PathfindHeuristicData = m_NetInitializeSystem.GetHeuristicData(),
			m_Actions = currentActions.m_Actions.AsArray(),
			m_ActionIndex = currentActions.m_ActionIndex
		};
		m_TransportLineSystem.GetMaxTransportSpeed(out jobData.m_MaxPassengerTransportSpeed, out jobData.m_MaxCargoTransportSpeed);
		for (int i = 0; i < num; i++)
		{
			JobHandle jobHandle = workerData.m_WriteHandle;
			ThreadData threadData = default(ThreadData);
			if (m_ThreadData.Count >= num2)
			{
				if (m_DependencyIndex >= count)
				{
					m_DependencyIndex = 0;
				}
				threadData = m_ThreadData[m_DependencyIndex];
				jobHandle = JobHandle.CombineDependencies(jobHandle, threadData.m_JobHandle);
			}
			else if (m_AllocatorPool.Count != 0)
			{
				threadData.m_Allocator = m_AllocatorPool[m_AllocatorPool.Count - 1];
				m_AllocatorPool.RemoveAt(m_AllocatorPool.Count - 1);
			}
			else
			{
				threadData.m_Allocator = new AllocatorHelper<UnsafeLinearAllocator>(Allocator.Persistent);
				threadData.m_Allocator.Allocator.Initialize(1048576u);
			}
			jobData.m_Allocator = threadData.m_Allocator;
			threadData.m_JobHandle = IJobExtensions.Schedule(jobData, jobHandle);
			currentActions.m_ReadHandle = JobHandle.CombineDependencies(currentActions.m_ReadHandle, threadData.m_JobHandle);
			if (m_ThreadData.Count >= num2)
			{
				m_ThreadData[m_DependencyIndex++] = threadData;
			}
			else
			{
				m_ThreadData.Add(threadData);
			}
		}
		workerData.m_ReadHandle = JobHandle.CombineDependencies(workerData.m_ReadHandle, currentActions.m_ReadHandle);
		currentActions = null;
		m_LastWorkerIndex = m_NextWorkerIndex;
	}
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

