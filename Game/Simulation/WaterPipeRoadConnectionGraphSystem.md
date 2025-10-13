# Game.Simulation.WaterPipeRoadConnectionGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeRoadConnectionGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem+TypeHandle __TypeHandle;

    public WaterPipeRoadConnectionGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> GetEdgeUpdateQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeRoadConnectionGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeRoadConnectionGraphSystem()`  

```csharp
[Preserve]
	public WaterPipeRoadConnectionGraphSystem()
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

- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddQueueWriter(JobHandle handle)
	{
		m_WriteDependencies = JobHandle.CombineDependencies(m_WriteDependencies, handle);
	}
```

- `public GetEdgeUpdateQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  

```csharp
public NativeQueue<Entity> GetEdgeUpdateQueue(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_UpdatedEdges;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_WaterPipeFlowSystem = base.World.GetOrCreateSystemManaged<WaterPipeFlowSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<RoadConnectionUpdated>());
		m_UpdatedEdges = new NativeQueue<Entity>(Allocator.Persistent);
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
		m_UpdatedEdges.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.Dependency = JobHandle.CombineDependencies(base.Dependency, m_WriteDependencies);
		if (!m_EventQuery.IsEmptyIgnoreFilter)
		{
			UpdateRoadConnectionsJob jobData = new UpdateRoadConnectionsJob
			{
				m_RoadConnectionUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_RoadConnectionUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WaterConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Deleted = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpdatedEdges = m_UpdatedEdges.AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_EventQuery, base.Dependency);
		}
		UpdateRoadEdgesJob jobData2 = new UpdateRoadEdgesJob
		{
			m_WaterConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeBuildingConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedBuildings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_ConnectedBuilding_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer(),
			m_UpdatedEdges = m_UpdatedEdges,
			m_SinkNode = m_WaterPipeFlowSystem.sinkNode,
			m_EdgeArchetype = m_WaterPipeFlowSystem.edgeArchetype
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		m_WriteDependencies = base.Dependency;
	}
```


## Nested types

- `Game.Simulation.WaterPipeRoadConnectionGraphSystem+UpdateRoadConnectionsJob`  
- `Game.Simulation.WaterPipeRoadConnectionGraphSystem+UpdateRoadEdgesJob`  
- `Game.Simulation.WaterPipeRoadConnectionGraphSystem+TypeHandle`  

