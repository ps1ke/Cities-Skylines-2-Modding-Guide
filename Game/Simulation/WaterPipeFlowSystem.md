# Game.Simulation.WaterPipeFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeFlowSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_NodeGroup;
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityArchetype m_NodeArchetype;
    private Unity.Entities.EntityArchetype m_EdgeArchetype;
    private Game.Simulation.WaterPipeFlowJob+Data m_FreshData;
    private Game.Simulation.WaterPipeFlowJob+Data m_SewageData;
    private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections;
    private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
    private Unity.Collections.NativeList<System.Int32> m_TradeNodes;
    private Unity.Entities.Entity m_SourceNode;
    private Unity.Entities.Entity m_SinkNode;
    private Game.Simulation.WaterPipeFlowSystem+Phase m_NextPhase;
    private Unity.Jobs.JobHandle m_DataDependency;
    private System.Boolean <ready>k__BackingField;
    private System.Boolean <fluidFlowEnabled>k__BackingField;
    private Game.Simulation.WaterPipeFlowSystem+TypeHandle __TypeHandle;
    public static const System.Int32 kUpdateInterval;
    public static const System.Int32 kUpdateOffset;
    public static const System.Int32 kUpdatesPerDay;
    public static const System.Int32 kStartFrames;
    public static const System.Int32 kAdjustFrame;
    public static const System.Int32 kPrepareFrame;
    public static const System.Int32 kFlowFrames;
    public static const System.Int32 kFlowCompletionFrame;
    public static const System.Int32 kEndFrames;
    public static const System.Int32 kApplyFrame;
    public static const System.Int32 kStatusFrame;
    public static const System.Int32 kMaxEdgeCapacity;
    private static const System.Int32 kLayerHeight;

    public System.Boolean ready { get; private set; }
    public Unity.Entities.EntityArchetype nodeArchetype { get; }
    public Unity.Entities.EntityArchetype edgeArchetype { get; }
    public Unity.Entities.Entity sourceNode { get; }
    public Unity.Entities.Entity sinkNode { get; }
    public System.Boolean fluidFlowEnabled { get; set; }

    public WaterPipeFlowSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void ApplyPhase();
    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void FlowPhase();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void PreparePhase();
    public System.Void Reset();
    private Unity.Jobs.JobHandle ScheduleFlowJob(Game.Simulation.WaterPipeFlowJob+Data jobData, System.Int32 importCapacity, System.Int32 exportCapacity, System.Boolean finalFrame);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_NodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_NodeGroup;
```

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Unity.Entities.EntityArchetype m_NodeArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_NodeArchetype;
```

- `private Unity.Entities.EntityArchetype m_EdgeArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EdgeArchetype;
```

- `private Game.Simulation.WaterPipeFlowJob+Data m_FreshData`  

```csharp
private Game.Simulation.WaterPipeFlowJob+Data m_FreshData;
```

- `private Game.Simulation.WaterPipeFlowJob+Data m_SewageData`  

```csharp
private Game.Simulation.WaterPipeFlowJob+Data m_SewageData;
```

- `private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections;
```

- `private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices`  

```csharp
private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
```

- `private Unity.Collections.NativeList<System.Int32> m_TradeNodes`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_TradeNodes;
```

- `private Unity.Entities.Entity m_SourceNode`  

```csharp
private Unity.Entities.Entity m_SourceNode;
```

- `private Unity.Entities.Entity m_SinkNode`  

```csharp
private Unity.Entities.Entity m_SinkNode;
```

- `private Game.Simulation.WaterPipeFlowSystem+Phase m_NextPhase`  

```csharp
private Game.Simulation.WaterPipeFlowSystem+Phase m_NextPhase;
```

- `private Unity.Jobs.JobHandle m_DataDependency`  

```csharp
private Unity.Jobs.JobHandle m_DataDependency;
```

- `private System.Boolean <ready>k__BackingField`  

```csharp
private System.Boolean <ready>k__BackingField;
```

- `private System.Boolean <fluidFlowEnabled>k__BackingField`  

```csharp
private System.Boolean <fluidFlowEnabled>k__BackingField;
```

- `private Game.Simulation.WaterPipeFlowSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeFlowSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 kUpdateInterval`  

```csharp
public static const System.Int32 kUpdateInterval;
```

- `public static const System.Int32 kUpdateOffset`  

```csharp
public static const System.Int32 kUpdateOffset;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```

- `public static const System.Int32 kStartFrames`  

```csharp
public static const System.Int32 kStartFrames;
```

- `public static const System.Int32 kAdjustFrame`  

```csharp
public static const System.Int32 kAdjustFrame;
```

- `public static const System.Int32 kPrepareFrame`  

```csharp
public static const System.Int32 kPrepareFrame;
```

- `public static const System.Int32 kFlowFrames`  

```csharp
public static const System.Int32 kFlowFrames;
```

- `public static const System.Int32 kFlowCompletionFrame`  

```csharp
public static const System.Int32 kFlowCompletionFrame;
```

- `public static const System.Int32 kEndFrames`  

```csharp
public static const System.Int32 kEndFrames;
```

- `public static const System.Int32 kApplyFrame`  

```csharp
public static const System.Int32 kApplyFrame;
```

- `public static const System.Int32 kStatusFrame`  

```csharp
public static const System.Int32 kStatusFrame;
```

- `public static const System.Int32 kMaxEdgeCapacity`  

```csharp
public static const System.Int32 kMaxEdgeCapacity;
```

- `private static const System.Int32 kLayerHeight`  

```csharp
private static const System.Int32 kLayerHeight;
```


## Properties

- `public System.Boolean ready { get; private set }`  

```csharp
public System.Boolean ready { get; private set; }
```

- `public Unity.Entities.EntityArchetype nodeArchetype { get }`  

```csharp
public Unity.Entities.EntityArchetype nodeArchetype { get; }
```

- `public Unity.Entities.EntityArchetype edgeArchetype { get }`  

```csharp
public Unity.Entities.EntityArchetype edgeArchetype { get; }
```

- `public Unity.Entities.Entity sourceNode { get }`  

```csharp
public Unity.Entities.Entity sourceNode { get; }
```

- `public Unity.Entities.Entity sinkNode { get }`  

```csharp
public Unity.Entities.Entity sinkNode { get; }
```

- `public System.Boolean fluidFlowEnabled { get; set }`  

```csharp
public System.Boolean fluidFlowEnabled { get; set; }
```


## Constructors

- `public WaterPipeFlowSystem()`  

```csharp
[Preserve]
	public WaterPipeFlowSystem()
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

- `private ApplyPhase() : System.Void`  

```csharp
private void ApplyPhase()
	{
		if (m_SimulationSystem.frameIndex % 128 == 62)
		{
			JobHandle dataDependency = JobChunkExtensions.ScheduleParallel(new ApplyEdgesJob
			{
				m_FlowEdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FreshEdges = m_FreshData.m_Edges.AsDeferredJobArray(),
				m_SewageEdges = m_SewageData.m_Edges.AsDeferredJobArray()
			}, m_EdgeGroup, JobHandle.CombineDependencies(base.Dependency, m_DataDependency));
			base.Dependency = (m_DataDependency = dataDependency);
			m_NextPhase = Phase.Prepare;
			ready = true;
		}
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private FlowPhase() : System.Void`  

```csharp
private void FlowPhase()
	{
		uint num = m_SimulationSystem.frameIndex % 128;
		Assert.IsTrue(num != 64 && num != 65 && num != 62 && num != 63);
		bool flag = num == 61;
		JobHandle job = ScheduleFlowJob(m_FreshData, 1073741823, 1073741823, flag);
		JobHandle job2 = ScheduleFlowJob(m_SewageData, 1073741823, 0, flag);
		m_DataDependency = JobHandle.CombineDependencies(job, job2);
		if (flag)
		{
			m_NextPhase = Phase.Apply;
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_NodeGroup = GetEntityQuery(ComponentType.ReadWrite<WaterPipeNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>(), ComponentType.Exclude<Deleted>());
		m_EdgeGroup = GetEntityQuery(ComponentType.ReadWrite<WaterPipeEdge>(), ComponentType.Exclude<Deleted>());
		m_NodeArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadOnly<WaterPipeNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>());
		m_EdgeArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadOnly<WaterPipeEdge>());
		m_FreshData = new WaterPipeFlowJob.Data(200000, Allocator.Persistent);
		m_SewageData = new WaterPipeFlowJob.Data(200000, Allocator.Persistent);
		m_Connections = new NativeList<Connection>(Allocator.Persistent);
		m_NodeIndices = new NativeReference<NodeIndices>(Allocator.Persistent);
		m_TradeNodes = new NativeList<int>(Allocator.Persistent);
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
		m_DataDependency.Complete();
		m_FreshData.Dispose();
		m_SewageData.Dispose();
		m_Connections.Dispose();
		m_NodeIndices.Dispose();
		m_TradeNodes.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_NextPhase == Phase.Prepare)
		{
			PreparePhase();
		}
		else if (m_NextPhase == Phase.Flow)
		{
			FlowPhase();
		}
		else if (m_NextPhase == Phase.Apply)
		{
			ApplyPhase();
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (m_SourceNode == Entity.Null && m_SinkNode == Entity.Null)
		{
			m_SourceNode = base.EntityManager.CreateEntity(m_NodeArchetype);
			m_SinkNode = base.EntityManager.CreateEntity(m_NodeArchetype);
		}
		Reset();
		DispatchWaterSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<DispatchWaterSystem>();
		if (context.version < Version.waterPipeFlowSim && context.purpose == Purpose.LoadGame)
		{
			UnityEngine.Debug.LogWarning("Detected legacy water pipes, disabling water & sewage notifications!");
			orCreateSystemManaged.freshConsumptionDisabled = true;
			orCreateSystemManaged.sewageConsumptionDisabled = true;
		}
		else
		{
			orCreateSystemManaged.freshConsumptionDisabled = false;
			orCreateSystemManaged.sewageConsumptionDisabled = false;
		}
		if (!(context.version < Version.waterPipePollution))
		{
			return;
		}
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<WaterPipeNodeConnection>());
		try
		{
			NativeArray<Entity> nativeArray = entityQuery.ToEntityArray(Allocator.Temp);
			NativeArray<WaterPipeNodeConnection> nativeArray2 = entityQuery.ToComponentDataArray<WaterPipeNodeConnection>(Allocator.Temp);
			for (int i = 0; i < nativeArray2.Length; i++)
			{
				if (nativeArray2[i].m_WaterPipeNode == Entity.Null)
				{
					COSystemBase.baseLog.WarnFormat("{0} has null WaterPipeNode! Removing...", nativeArray[i]);
					base.EntityManager.RemoveComponent<WaterPipeNodeConnection>(nativeArray[i]);
				}
			}
		}
		finally
		{
			entityQuery.Dispose();
		}
	}
```

- `private PreparePhase() : System.Void`  

```csharp
private void PreparePhase()
	{
		if (m_SimulationSystem.frameIndex % 128 == 65)
		{
			int chunkCapacity = m_NodeArchetype.ChunkCapacity;
			int chunkCapacity2 = m_EdgeArchetype.ChunkCapacity;
			int nodeCount = chunkCapacity * m_NodeGroup.CalculateChunkCountWithoutFiltering();
			int edgeCount = chunkCapacity2 * m_EdgeGroup.CalculateChunkCountWithoutFiltering();
			JobHandle dependsOn = IJobExtensions.Schedule(new PrepareNetworkJob
			{
				m_FreshNodes = m_FreshData.m_Nodes,
				m_SewageNodes = m_SewageData.m_Nodes,
				m_FreshEdges = m_FreshData.m_Edges,
				m_SewageEdges = m_SewageData.m_Edges,
				m_Connections = m_Connections,
				m_TradeNodes = m_TradeNodes,
				m_NodeCount = nodeCount,
				m_EdgeCount = edgeCount
			}, JobHandle.CombineDependencies(base.Dependency, m_DataDependency));
			JobHandle job = JobChunkExtensions.ScheduleParallel(new PrepareNodesJob
			{
				m_FlowNodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeNode_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MaxChunkCapacity = chunkCapacity
			}, m_NodeGroup, base.Dependency);
			JobHandle job2 = JobChunkExtensions.ScheduleParallel(new PrepareEdgesJob
			{
				m_FlowEdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FreshEdges = m_FreshData.m_Edges.AsDeferredJobArray(),
				m_SewageEdges = m_SewageData.m_Edges.AsDeferredJobArray(),
				m_MaxChunkCapacity = chunkCapacity2
			}, m_EdgeGroup, dependsOn);
			JobHandle job3 = JobChunkExtensions.Schedule(new PrepareConnectionsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ConnectedFlowEdgeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TradeNodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_TradeNode_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FlowNodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNode_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FreshNodes = m_FreshData.m_Nodes.AsDeferredJobArray(),
				m_SewageNodes = m_SewageData.m_Nodes.AsDeferredJobArray(),
				m_Connections = m_Connections,
				m_TradeNodes = m_TradeNodes,
				m_MaxChunkCapacity = chunkCapacity
			}, m_NodeGroup, JobHandle.CombineDependencies(job, job2));
			JobHandle job4 = IJobExtensions.Schedule(new PopulateNodeIndicesJob
			{
				m_FlowNodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNode_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeIndices = m_NodeIndices,
				m_SourceNode = m_SourceNode,
				m_SinkNode = m_SinkNode
			}, JobHandle.CombineDependencies(job, m_DataDependency));
			base.Dependency = (m_DataDependency = JobHandle.CombineDependencies(job3, job4));
			m_NextPhase = Phase.Flow;
		}
	}
```

- `public Reset() : System.Void`  

```csharp
public void Reset()
	{
		m_DataDependency.Complete();
		m_NextPhase = Phase.Prepare;
		m_FreshData.m_State.Value = new WaterPipeFlowJob.State(200000);
		m_SewageData.m_State.Value = new WaterPipeFlowJob.State(200000);
		ready = false;
	}
```

- `private ScheduleFlowJob(Game.Simulation.WaterPipeFlowJob+Data jobData, System.Int32 importCapacity, System.Int32 exportCapacity, System.Boolean finalFrame) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle ScheduleFlowJob(WaterPipeFlowJob.Data jobData, int importCapacity, int exportCapacity, bool finalFrame)
	{
		return IJobExtensions.Schedule(new WaterPipeFlowJob
		{
			m_State = jobData.m_State,
			m_Nodes = jobData.m_Nodes.AsDeferredJobArray(),
			m_Edges = jobData.m_Edges.AsDeferredJobArray(),
			m_Connections = m_Connections.AsDeferredJobArray(),
			m_NodeIndices = m_NodeIndices,
			m_TradeNodes = m_TradeNodes.AsDeferredJobArray(),
			m_MaxFlowState = jobData.m_MaxFlowState,
			m_LayerStates = jobData.m_LayerStates,
			m_LayerElements = jobData.m_LayerElements,
			m_LayerElementRefs = jobData.m_LayerElementRefs,
			m_FluidFlowState = jobData.m_FluidFlowState,
			m_ImportCapacity = importCapacity,
			m_ExportCapacity = exportCapacity,
			m_FluidFlowEnabled = fluidFlowEnabled,
			m_LayerHeight = 20,
			m_FrameCount = 1,
			m_FinalFrame = finalFrame
		}, m_DataDependency);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		Reset();
		m_SourceNode = Entity.Null;
		m_SinkNode = Entity.Null;
	}
```


## Nested types

- `Game.Simulation.WaterPipeFlowSystem+Phase`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareNetworkJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareNodesJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareEdgesJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareConnectionsJob`  
- `Game.Simulation.WaterPipeFlowSystem+PopulateNodeIndicesJob`  
- `Game.Simulation.WaterPipeFlowSystem+ApplyEdgesJob`  
- `Game.Simulation.WaterPipeFlowSystem+TypeHandle`  

