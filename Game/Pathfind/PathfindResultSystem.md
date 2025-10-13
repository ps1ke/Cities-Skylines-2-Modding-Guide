# Game.Pathfind.PathfindResultSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathfindResultSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityCommandBuffer m_CommandBuffer;
    private Unity.Entities.EntityArchetype m_PathEventArchetype;
    private Unity.Entities.EntityArchetype m_CoverageEventArchetype;
    private System.UInt32 m_PendingSimulationFrameIndex;
    private System.Int32 m_PendingRequestCount;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> m_ResultListIndex;
    private System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> m_QueryStats;
    private Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_PathfindResultBuffer;
    private Unity.Collections.NativeList<Game.Pathfind.CoverageJobs+ResultItem> m_CoverageResultBuffer;
    private Unity.Collections.NativeList<Game.Pathfind.AvailabilityJobs+ResultItem> m_AvailabilityResultBuffer;
    private Game.Pathfind.PathfindResultSystem+TypeHandle __TypeHandle;

    public System.UInt32 pendingSimulationFrame { get; }
    public System.Int32 pendingRequestCount { get; }
    public System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> queryStats { get; }

    public PathfindResultSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddQueryStats(System.Object system, Game.Pathfind.PathfindResultSystem+QueryType queryType, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType, System.Int32 resultLength, System.Int32 graphTraversal);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
    private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
    private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
    private System.Void ProcessResults<T>(Game.Pathfind.PathfindQueueSystem+ActionList<T> list);
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityCommandBuffer m_CommandBuffer`  

```csharp
private Unity.Entities.EntityCommandBuffer m_CommandBuffer;
```

- `private Unity.Entities.EntityArchetype m_PathEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PathEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_CoverageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_CoverageEventArchetype;
```

- `private System.UInt32 m_PendingSimulationFrameIndex`  

```csharp
private System.UInt32 m_PendingSimulationFrameIndex;
```

- `private System.Int32 m_PendingRequestCount`  

```csharp
private System.Int32 m_PendingRequestCount;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> m_ResultListIndex`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> m_ResultListIndex;
```

- `private System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> m_QueryStats`  

```csharp
private System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> m_QueryStats;
```

- `private Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_PathfindResultBuffer`  

```csharp
private Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_PathfindResultBuffer;
```

- `private Unity.Collections.NativeList<Game.Pathfind.CoverageJobs+ResultItem> m_CoverageResultBuffer`  

```csharp
private Unity.Collections.NativeList<Game.Pathfind.CoverageJobs+ResultItem> m_CoverageResultBuffer;
```

- `private Unity.Collections.NativeList<Game.Pathfind.AvailabilityJobs+ResultItem> m_AvailabilityResultBuffer`  

```csharp
private Unity.Collections.NativeList<Game.Pathfind.AvailabilityJobs+ResultItem> m_AvailabilityResultBuffer;
```

- `private Game.Pathfind.PathfindResultSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.PathfindResultSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.UInt32 pendingSimulationFrame { get }`  

```csharp
public System.UInt32 pendingSimulationFrame { get; }
```

- `public System.Int32 pendingRequestCount { get }`  

```csharp
public System.Int32 pendingRequestCount { get; }
```

- `public System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> queryStats { get }`  

```csharp
public System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> queryStats { get; }
```


## Constructors

- `public PathfindResultSystem()`  

```csharp
[Preserve]
	public PathfindResultSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private AddQueryStats(System.Object system, Game.Pathfind.PathfindResultSystem+QueryType queryType, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType, System.Int32 resultLength, System.Int32 graphTraversal) : System.Void`  

```csharp
private void AddQueryStats(object system, QueryType queryType, SetupTargetType originType, SetupTargetType destinationType, int resultLength, int graphTraversal)
	{
		ResultKey key = new ResultKey
		{
			m_System = system,
			m_QueryType = queryType,
			m_OriginType = originType,
			m_DestinationType = destinationType
		};
		if (m_QueryStats.TryGetValue(key, out var value))
		{
			value.m_QueryCount++;
			value.m_SuccessCount += math.min(1, resultLength);
			value.m_GraphTraversal += (float)graphTraversal / math.max(1f, m_PathfindQueueSystem.GetGraphSize());
			value.m_Efficiency += (float)resultLength / math.max(1f, graphTraversal);
			m_QueryStats[key] = value;
		}
		else
		{
			m_QueryStats.Add(key, new ResultValue
			{
				m_QueryCount = 1,
				m_SuccessCount = math.min(1, resultLength),
				m_GraphTraversal = (float)graphTraversal / math.max(1f, m_PathfindQueueSystem.GetGraphSize()),
				m_Efficiency = (float)resultLength / math.max(1f, graphTraversal)
			});
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_PathEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<PathUpdated>());
		m_CoverageEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<CoverageUpdated>());
		m_ResultListIndex = new Dictionary<Entity, int>(10);
		m_QueryStats = new Dictionary<ResultKey, ResultValue>(10);
		m_PathfindResultBuffer = new NativeList<PathfindJobs.ResultItem>(10, Allocator.Persistent);
		m_CoverageResultBuffer = new NativeList<CoverageJobs.ResultItem>(10, Allocator.Persistent);
		m_AvailabilityResultBuffer = new NativeList<AvailabilityJobs.ResultItem>(10, Allocator.Persistent);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_PathfindResultBuffer.Dispose();
		m_CoverageResultBuffer.Dispose();
		m_AvailabilityResultBuffer.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle outputDeps = base.Dependency;
		m_PendingSimulationFrameIndex = uint.MaxValue;
		m_PendingRequestCount = 0;
		m_CommandBuffer = default(EntityCommandBuffer);
		ProcessResults(m_PathfindQueueSystem.GetPathfindActions(), ref outputDeps, base.Dependency);
		ProcessResults(m_PathfindQueueSystem.GetCoverageActions(), ref outputDeps, base.Dependency);
		ProcessResults(m_PathfindQueueSystem.GetAvailabilityActions(), ref outputDeps, base.Dependency);
		ProcessResults(m_PathfindQueueSystem.GetCreateActions());
		ProcessResults(m_PathfindQueueSystem.GetUpdateActions());
		ProcessResults(m_PathfindQueueSystem.GetDeleteActions());
		ProcessResults(m_PathfindQueueSystem.GetDensityActions());
		ProcessResults(m_PathfindQueueSystem.GetTimeActions());
		ProcessResults(m_PathfindQueueSystem.GetFlowActions());
		base.Dependency = outputDeps;
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_PendingSimulationFrameIndex = uint.MaxValue;
		m_PendingRequestCount = 0;
		m_QueryStats.Clear();
	}
```

- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  

```csharp
private void ProcessResults(PathfindQueueSystem.ActionList<AvailabilityAction> list, ref JobHandle outputDeps, JobHandle inputDeps)
	{
		m_ResultListIndex.Clear();
		m_AvailabilityResultBuffer.Clear();
		int num = 0;
		AvailabilityJobs.ResultItem value2 = default(AvailabilityJobs.ResultItem);
		for (int i = 0; i < list.m_Items.Count; i++)
		{
			PathfindQueueSystem.ActionListItem<AvailabilityAction> value = list.m_Items[i];
			if ((value.m_Flags & PathFlags.Scheduled) != 0)
			{
				if (value.m_Action.data.m_State == PathfindActionState.Completed)
				{
					value.m_Flags &= ~PathFlags.Scheduled;
					value2.m_Owner = value.m_Owner;
					value2.m_Results = value.m_Action.data.m_Results;
					if (m_ResultListIndex.TryGetValue(value.m_Owner, out var value3))
					{
						m_AvailabilityResultBuffer[value3] = value2;
					}
					else
					{
						m_ResultListIndex.Add(value.m_Owner, m_AvailabilityResultBuffer.Length);
						m_AvailabilityResultBuffer.Add(in value2);
					}
					AddQueryStats(value.m_System, QueryType.Availability, SetupTargetType.None, SetupTargetType.None, value2.m_Results.Length, value2.m_Results.Length);
				}
				else
				{
					m_PendingSimulationFrameIndex = math.min(m_PendingSimulationFrameIndex, value.m_ResultFrame);
					m_PendingRequestCount++;
				}
			}
			else
			{
				if ((value.m_Flags & PathFlags.Pending) == 0)
				{
					value.Dispose();
					list.m_NextIndex--;
					continue;
				}
				m_PendingSimulationFrameIndex = math.min(m_PendingSimulationFrameIndex, value.m_ResultFrame);
				m_PendingRequestCount++;
			}
			list.m_Items[num++] = value;
		}
		if (num < list.m_Items.Count)
		{
			list.m_Items.RemoveRange(num, list.m_Items.Count - num);
		}
		if (m_AvailabilityResultBuffer.Length > 0)
		{
			JobHandle job = IJobParallelForExtensions.Schedule(new AvailabilityJobs.ProcessResultsJob
			{
				m_ResultItems = m_AvailabilityResultBuffer,
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AvailabilityElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_AvailabilityElement_RW_BufferLookup, ref base.CheckedStateRef)
			}, m_AvailabilityResultBuffer.Length, 1, inputDeps);
			outputDeps = JobHandle.CombineDependencies(outputDeps, job);
		}
	}
```

- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  

```csharp
private void ProcessResults(PathfindQueueSystem.ActionList<AvailabilityAction> list, ref JobHandle outputDeps, JobHandle inputDeps)
	{
		m_ResultListIndex.Clear();
		m_AvailabilityResultBuffer.Clear();
		int num = 0;
		AvailabilityJobs.ResultItem value2 = default(AvailabilityJobs.ResultItem);
		for (int i = 0; i < list.m_Items.Count; i++)
		{
			PathfindQueueSystem.ActionListItem<AvailabilityAction> value = list.m_Items[i];
			if ((value.m_Flags & PathFlags.Scheduled) != 0)
			{
				if (value.m_Action.data.m_State == PathfindActionState.Completed)
				{
					value.m_Flags &= ~PathFlags.Scheduled;
					value2.m_Owner = value.m_Owner;
					value2.m_Results = value.m_Action.data.m_Results;
					if (m_ResultListIndex.TryGetValue(value.m_Owner, out var value3))
					{
						m_AvailabilityResultBuffer[value3] = value2;
					}
					else
					{
						m_ResultListIndex.Add(value.m_Owner, m_AvailabilityResultBuffer.Length);
						m_AvailabilityResultBuffer.Add(in value2);
					}
					AddQueryStats(value.m_System, QueryType.Availability, SetupTargetType.None, SetupTargetType.None, value2.m_Results.Length, value2.m_Results.Length);
				}
				else
				{
					m_PendingSimulationFrameIndex = math.min(m_PendingSimulationFrameIndex, value.m_ResultFrame);
					m_PendingRequestCount++;
				}
			}
			else
			{
				if ((value.m_Flags & PathFlags.Pending) == 0)
				{
					value.Dispose();
					list.m_NextIndex--;
					continue;
				}
				m_PendingSimulationFrameIndex = math.min(m_PendingSimulationFrameIndex, value.m_ResultFrame);
				m_PendingRequestCount++;
			}
			list.m_Items[num++] = value;
		}
		if (num < list.m_Items.Count)
		{
			list.m_Items.RemoveRange(num, list.m_Items.Count - num);
		}
		if (m_AvailabilityResultBuffer.Length > 0)
		{
			JobHandle job = IJobParallelForExtensions.Schedule(new AvailabilityJobs.ProcessResultsJob
			{
				m_ResultItems = m_AvailabilityResultBuffer,
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AvailabilityElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_AvailabilityElement_RW_BufferLookup, ref base.CheckedStateRef)
			}, m_AvailabilityResultBuffer.Length, 1, inputDeps);
			outputDeps = JobHandle.CombineDependencies(outputDeps, job);
		}
	}
```

- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  

```csharp
private void ProcessResults(PathfindQueueSystem.ActionList<AvailabilityAction> list, ref JobHandle outputDeps, JobHandle inputDeps)
	{
		m_ResultListIndex.Clear();
		m_AvailabilityResultBuffer.Clear();
		int num = 0;
		AvailabilityJobs.ResultItem value2 = default(AvailabilityJobs.ResultItem);
		for (int i = 0; i < list.m_Items.Count; i++)
		{
			PathfindQueueSystem.ActionListItem<AvailabilityAction> value = list.m_Items[i];
			if ((value.m_Flags & PathFlags.Scheduled) != 0)
			{
				if (value.m_Action.data.m_State == PathfindActionState.Completed)
				{
					value.m_Flags &= ~PathFlags.Scheduled;
					value2.m_Owner = value.m_Owner;
					value2.m_Results = value.m_Action.data.m_Results;
					if (m_ResultListIndex.TryGetValue(value.m_Owner, out var value3))
					{
						m_AvailabilityResultBuffer[value3] = value2;
					}
					else
					{
						m_ResultListIndex.Add(value.m_Owner, m_AvailabilityResultBuffer.Length);
						m_AvailabilityResultBuffer.Add(in value2);
					}
					AddQueryStats(value.m_System, QueryType.Availability, SetupTargetType.None, SetupTargetType.None, value2.m_Results.Length, value2.m_Results.Length);
				}
				else
				{
					m_PendingSimulationFrameIndex = math.min(m_PendingSimulationFrameIndex, value.m_ResultFrame);
					m_PendingRequestCount++;
				}
			}
			else
			{
				if ((value.m_Flags & PathFlags.Pending) == 0)
				{
					value.Dispose();
					list.m_NextIndex--;
					continue;
				}
				m_PendingSimulationFrameIndex = math.min(m_PendingSimulationFrameIndex, value.m_ResultFrame);
				m_PendingRequestCount++;
			}
			list.m_Items[num++] = value;
		}
		if (num < list.m_Items.Count)
		{
			list.m_Items.RemoveRange(num, list.m_Items.Count - num);
		}
		if (m_AvailabilityResultBuffer.Length > 0)
		{
			JobHandle job = IJobParallelForExtensions.Schedule(new AvailabilityJobs.ProcessResultsJob
			{
				m_ResultItems = m_AvailabilityResultBuffer,
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AvailabilityElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_AvailabilityElement_RW_BufferLookup, ref base.CheckedStateRef)
			}, m_AvailabilityResultBuffer.Length, 1, inputDeps);
			outputDeps = JobHandle.CombineDependencies(outputDeps, job);
		}
	}
```

- `private ProcessResults<T>(Game.Pathfind.PathfindQueueSystem+ActionList<T> list) : System.Void`  

```csharp
private System.Void ProcessResults<T>(Game.Pathfind.PathfindQueueSystem+ActionList<T> list);
```


## Nested types

- `Game.Pathfind.PathfindResultSystem+QueryType`  
- `Game.Pathfind.PathfindResultSystem+ResultKey`  
- `Game.Pathfind.PathfindResultSystem+ResultValue`  
- `Game.Pathfind.PathfindResultSystem+TypeHandle`  

