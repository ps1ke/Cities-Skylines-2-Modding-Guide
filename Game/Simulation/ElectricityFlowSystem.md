# Game.Simulation.ElectricityFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityFlowSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_NodeGroup;
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityArchetype m_NodeArchetype;
    private Unity.Entities.EntityArchetype m_ChargeNodeArchetype;
    private Unity.Entities.EntityArchetype m_DischargeNodeArchetype;
    private Unity.Entities.EntityArchetype m_EdgeArchetype;
    private Unity.Collections.NativeList<Game.Simulation.Flow.Node> m_Nodes;
    private Unity.Collections.NativeList<Game.Simulation.Flow.Edge> m_Edges;
    private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections;
    private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
    private Unity.Collections.NativeList<System.Int32> m_ChargeNodes;
    private Unity.Collections.NativeList<System.Int32> m_DischargeNodes;
    private Unity.Collections.NativeList<System.Int32> m_TradeNodes;
    private Unity.Collections.NativeReference<Game.Simulation.ElectricityFlowJob+State> m_FlowJobState;
    private Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_SolverState;
    private Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates;
    private Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements;
    private Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs;
    private Unity.Entities.Entity m_SourceNode;
    private Unity.Entities.Entity m_SinkNode;
    private Unity.Entities.Entity m_LegacyOutsideSourceNode;
    private Unity.Entities.Entity m_LegacyOutsideSinkNode;
    private Game.Simulation.ElectricityFlowSystem+Phase m_NextPhase;
    private Unity.Jobs.JobHandle m_DataDependency;
    private System.Boolean <ready>k__BackingField;
    private Game.Simulation.ElectricityFlowSystem+TypeHandle __TypeHandle;
    public static const System.Int32 kUpdateInterval;
    public static const System.Int32 kUpdatesPerDay;
    public static const System.Int32 kUpdatesPerHour;
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
    public Unity.Entities.EntityArchetype chargeNodeArchetype { get; }
    public Unity.Entities.EntityArchetype dischargeNodeArchetype { get; }
    public Unity.Entities.EntityArchetype edgeArchetype { get; }
    public Unity.Entities.Entity sourceNode { get; }
    public Unity.Entities.Entity sinkNode { get; }

    public ElectricityFlowSystem();

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

- `private Unity.Entities.EntityArchetype m_ChargeNodeArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ChargeNodeArchetype;
```

- `private Unity.Entities.EntityArchetype m_DischargeNodeArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DischargeNodeArchetype;
```

- `private Unity.Entities.EntityArchetype m_EdgeArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EdgeArchetype;
```

- `private Unity.Collections.NativeList<Game.Simulation.Flow.Node> m_Nodes`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.Flow.Node> m_Nodes;
```

- `private Unity.Collections.NativeList<Game.Simulation.Flow.Edge> m_Edges`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.Flow.Edge> m_Edges;
```

- `private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections;
```

- `private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices`  

```csharp
private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
```

- `private Unity.Collections.NativeList<System.Int32> m_ChargeNodes`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_ChargeNodes;
```

- `private Unity.Collections.NativeList<System.Int32> m_DischargeNodes`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_DischargeNodes;
```

- `private Unity.Collections.NativeList<System.Int32> m_TradeNodes`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_TradeNodes;
```

- `private Unity.Collections.NativeReference<Game.Simulation.ElectricityFlowJob+State> m_FlowJobState`  

```csharp
private Unity.Collections.NativeReference<Game.Simulation.ElectricityFlowJob+State> m_FlowJobState;
```

- `private Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_SolverState`  

```csharp
private Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_SolverState;
```

- `private Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates;
```

- `private Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements;
```

- `private Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs;
```

- `private Unity.Entities.Entity m_SourceNode`  

```csharp
private Unity.Entities.Entity m_SourceNode;
```

- `private Unity.Entities.Entity m_SinkNode`  

```csharp
private Unity.Entities.Entity m_SinkNode;
```

- `private Unity.Entities.Entity m_LegacyOutsideSourceNode`  

```csharp
private Unity.Entities.Entity m_LegacyOutsideSourceNode;
```

- `private Unity.Entities.Entity m_LegacyOutsideSinkNode`  

```csharp
private Unity.Entities.Entity m_LegacyOutsideSinkNode;
```

- `private Game.Simulation.ElectricityFlowSystem+Phase m_NextPhase`  

```csharp
private Game.Simulation.ElectricityFlowSystem+Phase m_NextPhase;
```

- `private Unity.Jobs.JobHandle m_DataDependency`  

```csharp
private Unity.Jobs.JobHandle m_DataDependency;
```

- `private System.Boolean <ready>k__BackingField`  

```csharp
private System.Boolean <ready>k__BackingField;
```

- `private Game.Simulation.ElectricityFlowSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityFlowSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 kUpdateInterval`  

```csharp
public static const System.Int32 kUpdateInterval;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```

- `public static const System.Int32 kUpdatesPerHour`  

```csharp
public static const System.Int32 kUpdatesPerHour;
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

- `public Unity.Entities.EntityArchetype chargeNodeArchetype { get }`  

```csharp
public Unity.Entities.EntityArchetype chargeNodeArchetype { get; }
```

- `public Unity.Entities.EntityArchetype dischargeNodeArchetype { get }`  

```csharp
public Unity.Entities.EntityArchetype dischargeNodeArchetype { get; }
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


## Constructors

- `public ElectricityFlowSystem()`  

```csharp
[Preserve]
	public ElectricityFlowSystem()
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
		Assert.IsFalse(m_SimulationSystem.frameIndex % 128 > 126);
		if (m_SimulationSystem.frameIndex % 128 == 126)
		{
			JobHandle dataDependency = JobChunkExtensions.ScheduleParallel(new ApplyEdgesJob
			{
				m_FlowEdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Edges = m_Edges.AsDeferredJobArray()
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
		Assert.IsTrue(num != 0 && num != 1 && num != 126 && num != 127);
		bool flag = num >= 125;
		ElectricityFlowJob jobData = new ElectricityFlowJob
		{
			m_State = m_FlowJobState,
			m_Nodes = m_Nodes.AsDeferredJobArray(),
			m_Edges = m_Edges.AsDeferredJobArray(),
			m_Connections = m_Connections.AsDeferredJobArray(),
			m_NodeIndices = m_NodeIndices,
			m_ChargeNodes = m_ChargeNodes.AsDeferredJobArray(),
			m_DischargeNodes = m_DischargeNodes.AsDeferredJobArray(),
			m_TradeNodes = m_TradeNodes.AsDeferredJobArray(),
			m_SolverState = m_SolverState,
			m_LayerStates = m_LayerStates,
			m_LayerElements = m_LayerElements,
			m_LayerElementRefs = m_LayerElementRefs,
			m_LabelQueue = new NativeQueue<int>(Allocator.TempJob),
			m_LayerHeight = 20,
			m_FrameCount = 1,
			m_FinalFrame = flag
		};
		JobHandle jobHandle = IJobExtensions.Schedule(jobData, m_DataDependency);
		jobData.m_LabelQueue.Dispose(jobHandle);
		m_DataDependency = jobHandle;
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
		m_NodeGroup = GetEntityQuery(ComponentType.ReadWrite<ElectricityFlowNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>(), ComponentType.Exclude<Deleted>());
		m_EdgeGroup = GetEntityQuery(ComponentType.ReadWrite<ElectricityFlowEdge>(), ComponentType.Exclude<Deleted>());
		m_NodeArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadOnly<ElectricityFlowNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>());
		m_ChargeNodeArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadOnly<ElectricityFlowNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>(), ComponentType.ReadOnly<BatteryChargeNode>());
		m_DischargeNodeArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadOnly<ElectricityFlowNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>(), ComponentType.ReadOnly<BatteryDischargeNode>());
		m_EdgeArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadOnly<ElectricityFlowEdge>());
		m_Nodes = new NativeList<Game.Simulation.Flow.Node>(Allocator.Persistent);
		m_Edges = new NativeList<Game.Simulation.Flow.Edge>(Allocator.Persistent);
		m_Connections = new NativeList<Connection>(Allocator.Persistent);
		m_NodeIndices = new NativeReference<NodeIndices>(Allocator.Persistent);
		m_ChargeNodes = new NativeList<int>(Allocator.Persistent);
		m_DischargeNodes = new NativeList<int>(Allocator.Persistent);
		m_TradeNodes = new NativeList<int>(Allocator.Persistent);
		m_FlowJobState = new NativeReference<ElectricityFlowJob.State>(new ElectricityFlowJob.State(20000), Allocator.Persistent);
		m_SolverState = new NativeReference<MaxFlowSolverState>(default(MaxFlowSolverState), Allocator.Persistent);
		m_LayerStates = new NativeList<LayerState>(Allocator.Persistent);
		m_LayerElements = new NativeList<CutElement>(Allocator.Persistent);
		m_LayerElementRefs = new NativeList<CutElementRef>(Allocator.Persistent);
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
		m_Nodes.Dispose();
		m_Edges.Dispose();
		m_Connections.Dispose();
		m_NodeIndices.Dispose();
		m_ChargeNodes.Dispose();
		m_DischargeNodes.Dispose();
		m_TradeNodes.Dispose();
		m_FlowJobState.Dispose();
		m_SolverState.Dispose();
		m_LayerStates.Dispose();
		m_LayerElements.Dispose();
		m_LayerElementRefs.Dispose();
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
		if (context.purpose == Purpose.NewMap || (context.purpose == Purpose.NewGame && context.version < Version.timoSerializationFlow) || (context.purpose == Purpose.LoadMap && m_SourceNode == Entity.Null))
		{
			m_SourceNode = base.EntityManager.CreateEntity(m_NodeArchetype);
			m_SinkNode = base.EntityManager.CreateEntity(m_NodeArchetype);
		}
		if (m_LegacyOutsideSourceNode != Entity.Null || m_LegacyOutsideSinkNode != Entity.Null)
		{
			if (m_LegacyOutsideSourceNode != Entity.Null)
			{
				ElectricityGraphUtils.DeleteFlowNode(base.EntityManager, m_LegacyOutsideSourceNode);
			}
			if (m_LegacyOutsideSinkNode != Entity.Null)
			{
				ElectricityGraphUtils.DeleteFlowNode(base.EntityManager, m_LegacyOutsideSinkNode);
			}
			NativeArray<Entity> nativeArray = m_EdgeGroup.ToEntityArray(Allocator.TempJob);
			NativeArray<ElectricityFlowEdge> nativeArray2 = m_EdgeGroup.ToComponentDataArray<ElectricityFlowEdge>(Allocator.TempJob);
			try
			{
				for (int i = 0; i < nativeArray.Length; i++)
				{
					Entity entity = nativeArray[i];
					ElectricityFlowEdge electricityFlowEdge = nativeArray2[i];
					if (electricityFlowEdge.m_Start == m_LegacyOutsideSourceNode || electricityFlowEdge.m_End == m_LegacyOutsideSourceNode)
					{
						base.EntityManager.AddComponent<Deleted>(entity);
					}
					else if (electricityFlowEdge.m_Start == m_LegacyOutsideSinkNode || electricityFlowEdge.m_End == m_LegacyOutsideSinkNode)
					{
						base.EntityManager.AddComponent<Deleted>(entity);
					}
				}
			}
			finally
			{
				nativeArray.Dispose();
				nativeArray2.Dispose();
			}
			m_LegacyOutsideSourceNode = Entity.Null;
			m_LegacyOutsideSinkNode = Entity.Null;
			EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<ElectricityOutsideConnection>(), ComponentType.ReadOnly<Owner>(), ComponentType.Exclude<Temp>());
			NativeArray<Owner> nativeArray3 = entityQuery.ToComponentDataArray<Owner>(Allocator.TempJob);
			try
			{
				foreach (Owner item in nativeArray3)
				{
					if (base.EntityManager.TryGetComponent<ElectricityNodeConnection>(item.m_Owner, out var component))
					{
						base.EntityManager.AddComponent<TradeNode>(component.m_ElectricityNode);
						ElectricityGraphUtils.CreateFlowEdge(base.EntityManager, m_EdgeArchetype, m_SourceNode, component.m_ElectricityNode, FlowDirection.None, 1073741823);
						ElectricityGraphUtils.CreateFlowEdge(base.EntityManager, m_EdgeArchetype, component.m_ElectricityNode, m_SinkNode, FlowDirection.None, 1073741823);
					}
				}
			}
			finally
			{
				entityQuery.Dispose();
				nativeArray3.Dispose();
			}
		}
		Reset();
	}
```

- `private PreparePhase() : System.Void`  

```csharp
private void PreparePhase()
	{
		if (m_SimulationSystem.frameIndex % 128 == 1)
		{
			int chunkCapacity = m_NodeArchetype.ChunkCapacity;
			int chunkCapacity2 = m_EdgeArchetype.ChunkCapacity;
			int nodeCount = chunkCapacity * m_NodeGroup.CalculateChunkCountWithoutFiltering();
			int edgeCount = chunkCapacity2 * m_EdgeGroup.CalculateChunkCountWithoutFiltering();
			JobHandle dependsOn = IJobExtensions.Schedule(new PrepareNetworkJob
			{
				m_Nodes = m_Nodes,
				m_Edges = m_Edges,
				m_Connections = m_Connections,
				m_ChargeNodes = m_ChargeNodes,
				m_DischargeNodes = m_DischargeNodes,
				m_TradeNodes = m_TradeNodes,
				m_NodeCount = nodeCount,
				m_EdgeCount = edgeCount
			}, JobHandle.CombineDependencies(base.Dependency, m_DataDependency));
			JobHandle job = JobChunkExtensions.ScheduleParallel(new PrepareNodesJob
			{
				m_FlowNodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityFlowNode_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MaxChunkCapacity = chunkCapacity
			}, m_NodeGroup, base.Dependency);
			JobHandle job2 = JobChunkExtensions.ScheduleParallel(new PrepareEdgesJob
			{
				m_FlowEdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Edges = m_Edges.AsDeferredJobArray(),
				m_MaxChunkCapacity = chunkCapacity2
			}, m_EdgeGroup, dependsOn);
			JobHandle job3 = JobChunkExtensions.Schedule(new PrepareConnectionsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ConnectedFlowEdgeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_ChargeNodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_BatteryChargeNode_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DischargeNodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_BatteryDischargeNode_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TradeNodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_TradeNode_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FlowNodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowNode_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Nodes = m_Nodes.AsDeferredJobArray(),
				m_Connections = m_Connections,
				m_ChargeNodes = m_ChargeNodes,
				m_DischargeNodes = m_DischargeNodes,
				m_TradeNodes = m_TradeNodes,
				m_MaxChunkCapacity = chunkCapacity
			}, m_NodeGroup, JobHandle.CombineDependencies(job, job2));
			JobHandle job4 = IJobExtensions.Schedule(new PopulateNodeIndicesJob
			{
				m_FlowNodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowNode_RO_ComponentLookup, ref base.CheckedStateRef),
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
		m_FlowJobState.Value = new ElectricityFlowJob.State(20000);
		ready = false;
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

- `Game.Simulation.ElectricityFlowSystem+Phase`  
- `Game.Simulation.ElectricityFlowSystem+PrepareNetworkJob`  
- `Game.Simulation.ElectricityFlowSystem+PrepareNodesJob`  
- `Game.Simulation.ElectricityFlowSystem+PrepareEdgesJob`  
- `Game.Simulation.ElectricityFlowSystem+PrepareConnectionsJob`  
- `Game.Simulation.ElectricityFlowSystem+PopulateNodeIndicesJob`  
- `Game.Simulation.ElectricityFlowSystem+ApplyEdgesJob`  
- `Game.Simulation.ElectricityFlowSystem+TypeHandle`  

