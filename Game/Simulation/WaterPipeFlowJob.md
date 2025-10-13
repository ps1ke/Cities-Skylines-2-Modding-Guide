# Game.Simulation.WaterPipeFlowJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct WaterPipeFlowJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeReference<Game.Simulation.WaterPipeFlowJob+State> m_State;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections;
    public Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
    public Unity.Collections.NativeArray<System.Int32> m_TradeNodes;
    public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_MaxFlowState;
    public Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates;
    public Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements;
    public Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs;
    public Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> m_FluidFlowState;
    public System.Int32 m_ImportCapacity;
    public System.Int32 m_ExportCapacity;
    public System.Boolean m_FluidFlowEnabled;
    public System.Int32 m_LayerHeight;
    public System.Int32 m_FrameCount;
    public System.Boolean m_FinalFrame;
    private static const System.Int32 kShortageNodeLabel;
    private static const System.Int32 kConnectedNodeLabel;
    public static const System.Int32 kShortageEdgeLabel;
    public static const System.Int32 kConnectedEdgeLabel;
    private static const System.Int32 kSinkEdgeLabel;

    private System.Void EnableTradeConnections();
    public System.Void Execute();
    private System.Void ExecutePhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps);
    private System.Void Finalize(Game.Simulation.WaterPipeFlowJob+State& state);
    private System.Void FinalizeFlows();
    private System.Void FluidFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps);
    private System.Void InitialPhase(Game.Simulation.WaterPipeFlowJob+State& state);
    private System.Void LabelConnected(Game.Simulation.WaterPipeFlowJob+State& state);
    private System.Void LabelConnectedSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue);
    private System.Void LabelShortages(Game.Simulation.WaterPipeFlowJob+State& state);
    private System.Void LabelShortageSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue);
    private System.Void LimitImportEdgeCapacity();
    private System.Void MaxFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.WaterPipeFlowJob+Phase phaseAfterCompletion);
    private System.Void PostProducerPhase(Game.Simulation.WaterPipeFlowJob+State& state);
    private System.Void PostTradePhase(Game.Simulation.WaterPipeFlowJob+State& state);
    private System.Void PreflowSinkEdges();
    private System.Void ResetMaxFlowState();
    private System.Void ResetNonSinkEdges();
    private System.Void SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export);
}
```


## Fields

- `public Unity.Collections.NativeReference<Game.Simulation.WaterPipeFlowJob+State> m_State`  

```csharp
public Unity.Collections.NativeReference<Game.Simulation.WaterPipeFlowJob+State> m_State;
```

- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes;
```

- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges;
```

- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections;
```

- `public Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices`  

```csharp
public Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
```

- `public Unity.Collections.NativeArray<System.Int32> m_TradeNodes`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_TradeNodes;
```

- `public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_MaxFlowState`  

```csharp
public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_MaxFlowState;
```

- `public Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates;
```

- `public Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements;
```

- `public Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs;
```

- `public Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> m_FluidFlowState`  

```csharp
public Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> m_FluidFlowState;
```

- `public System.Int32 m_ImportCapacity`  

```csharp
public System.Int32 m_ImportCapacity;
```

- `public System.Int32 m_ExportCapacity`  

```csharp
public System.Int32 m_ExportCapacity;
```

- `public System.Boolean m_FluidFlowEnabled`  

```csharp
public System.Boolean m_FluidFlowEnabled;
```

- `public System.Int32 m_LayerHeight`  

```csharp
public System.Int32 m_LayerHeight;
```

- `public System.Int32 m_FrameCount`  

```csharp
public System.Int32 m_FrameCount;
```

- `public System.Boolean m_FinalFrame`  

```csharp
public System.Boolean m_FinalFrame;
```

- `private static const System.Int32 kShortageNodeLabel`  

```csharp
private static const System.Int32 kShortageNodeLabel;
```

- `private static const System.Int32 kConnectedNodeLabel`  

```csharp
private static const System.Int32 kConnectedNodeLabel;
```

- `public static const System.Int32 kShortageEdgeLabel`  

```csharp
public static const System.Int32 kShortageEdgeLabel;
```

- `public static const System.Int32 kConnectedEdgeLabel`  

```csharp
public static const System.Int32 kConnectedEdgeLabel;
```

- `private static const System.Int32 kSinkEdgeLabel`  

```csharp
private static const System.Int32 kSinkEdgeLabel;
```


## Methods

- `private EnableTradeConnections() : System.Void`  

```csharp
private void EnableTradeConnections()
	{
		NodeIndices value = m_NodeIndices.Value;
		foreach (int tradeNode in m_TradeNodes)
		{
			Game.Simulation.Flow.Node node = m_Nodes[tradeNode];
			bool flag = node.m_CutElementId.m_Version == -1;
			for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
			{
				Connection connection = m_Connections[i];
				ref Game.Simulation.Flow.Edge reference = ref m_Edges.ElementAt(connection.m_Edge);
				if (connection.m_EndNode == value.m_SourceNode)
				{
					Assert.IsTrue(connection.m_Backwards);
					reference.m_Capacity = (flag ? m_ImportCapacity : 0);
				}
				else if (connection.m_EndNode == value.m_SinkNode)
				{
					Assert.IsFalse(connection.m_Backwards);
					reference.m_Capacity = ((!flag) ? m_ExportCapacity : 0);
				}
			}
		}
	}
```

- `public Execute() : System.Void`  

```csharp
public void Execute()
	{
		ref State reference = ref m_State.ValueAsRef();
		if (reference.m_Error)
		{
			if (m_FinalFrame)
			{
				UnityEngine.Debug.LogError($"Water pipe solver error in phase: {reference.m_Phase}");
				Finalize(ref reference);
			}
			return;
		}
		reference.m_Error = true;
		int num = math.max(100, reference.m_LastTotalSteps / 124);
		int num2 = reference.m_StepCounter + m_FrameCount * num;
		while (reference.m_Phase != Phase.Complete && (m_FinalFrame || reference.m_StepCounter < num2))
		{
			ExecutePhase(ref reference, num2);
		}
		reference.m_Error = false;
		if (m_FinalFrame)
		{
			Finalize(ref reference);
		}
	}
```

- `private ExecutePhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps) : System.Void`  

```csharp
private void ExecutePhase(ref State state, int maxSteps)
	{
		if (state.m_Phase == Phase.Initial)
		{
			InitialPhase(ref state);
			return;
		}
		if (state.m_Phase == Phase.Producer)
		{
			MaxFlowPhase(ref state, maxSteps, Phase.PostProducer);
			return;
		}
		if (state.m_Phase == Phase.PostProducer)
		{
			PostProducerPhase(ref state);
			return;
		}
		if (state.m_Phase == Phase.Trade)
		{
			MaxFlowPhase(ref state, maxSteps, Phase.PostTrade);
			return;
		}
		if (state.m_Phase == Phase.PostTrade)
		{
			PostTradePhase(ref state);
			return;
		}
		if (state.m_Phase == Phase.FluidFlow)
		{
			FluidFlowPhase(ref state, maxSteps);
			return;
		}
		throw new Exception("Invalid phase");
	}
```

- `private Finalize(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private void Finalize(ref State state)
	{
		state.m_Phase = Phase.Initial;
		state.m_LastTotalSteps = state.m_StepCounter;
		state.m_StepCounter = 0;
		state.m_Error = false;
	}
```

- `private FinalizeFlows() : System.Void`  

```csharp
private void FinalizeFlows()
	{
		for (int i = 0; i < m_Edges.Length; i++)
		{
			m_Edges.ElementAt(i).FinalizeTempFlow();
		}
	}
```

- `private FluidFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps) : System.Void`  

```csharp
private void FluidFlowPhase(ref State state, int maxSteps)
	{
		NodeIndices value = m_NodeIndices.Value;
		FluidFlowSolver fluidFlowSolver = new FluidFlowSolver
		{
			m_SourceNode = value.m_SourceNode,
			m_SinkNode = value.m_SinkNode,
			m_Nodes = m_Nodes,
			m_Edges = m_Edges,
			m_Connections = m_Connections,
			m_LabelQueue = new NativeMinHeap<LabelHeapData>(256, Allocator.Temp),
			m_PushQueue = new NativeMinHeap<PushHeapData>(2048, Allocator.Temp),
			m_StepCounter = state.m_StepCounter
		};
		if (m_FluidFlowState.Value.m_CurrentVersion == 0)
		{
			fluidFlowSolver.InitializeState();
		}
		else
		{
			fluidFlowSolver.LoadState(m_FluidFlowState);
		}
		while (!fluidFlowSolver.m_Complete && (m_FinalFrame || fluidFlowSolver.m_StepCounter < maxSteps))
		{
			fluidFlowSolver.SolveStep();
		}
		fluidFlowSolver.SaveState(m_FluidFlowState);
		fluidFlowSolver.m_LabelQueue.Dispose();
		fluidFlowSolver.m_PushQueue.Dispose();
		state.m_StepCounter = fluidFlowSolver.m_StepCounter;
		if (fluidFlowSolver.m_Complete)
		{
			state.m_Phase = Phase.Complete;
		}
	}
```

- `private InitialPhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private void InitialPhase(ref State state)
	{
		ResetMaxFlowState();
		state.m_Phase = Phase.Producer;
	}
```

- `private LabelConnected(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private void LabelConnected(ref State state)
	{
		NativeQueue<int> labelQueue = new NativeQueue<int>(Allocator.Temp);
		NodeIndices value = m_NodeIndices.Value;
		Game.Simulation.Flow.Node node = m_Nodes[value.m_SourceNode];
		for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
		{
			Connection connection = m_Connections[i];
			if (m_Nodes[connection.m_EndNode].m_CutElementId.m_Version == -2)
			{
				m_Edges.ElementAt(connection.m_Edge).m_CutElementId = new Identifier(connection.m_EndNode, -2);
			}
			else if (connection.GetOutgoingCapacity(m_Edges) > 0)
			{
				m_Edges.ElementAt(connection.m_Edge).m_CutElementId = new Identifier(connection.m_EndNode, -2);
				LabelConnectedSubGraph(ref state, connection.m_EndNode, labelQueue);
			}
		}
		labelQueue.Dispose();
	}
```

- `private LabelConnectedSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue) : System.Void`  

```csharp
private void LabelConnectedSubGraph(ref State state, int initialNodeIndex, NativeQueue<int> labelQueue)
	{
		NodeIndices value = m_NodeIndices.Value;
		Assert.IsTrue(labelQueue.IsEmpty());
		Identifier identifier = new Identifier(initialNodeIndex, -2);
		Identifier cutElementId = new Identifier(initialNodeIndex, -2);
		m_Nodes.ElementAt(initialNodeIndex).m_CutElementId = identifier;
		labelQueue.Enqueue(initialNodeIndex);
		int item;
		while (labelQueue.TryDequeue(out item))
		{
			state.m_StepCounter++;
			Game.Simulation.Flow.Node node = m_Nodes[item];
			Assert.AreEqual(identifier, node.m_CutElementId);
			for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
			{
				Connection connection = m_Connections[i];
				int endNode = connection.m_EndNode;
				if (connection.GetOutgoingCapacity(m_Edges) <= 0 && endNode != value.m_SinkNode)
				{
					continue;
				}
				m_Edges.ElementAt(connection.m_Edge).m_CutElementId = cutElementId;
				if (endNode != value.m_SinkNode && endNode != value.m_SourceNode)
				{
					ref Game.Simulation.Flow.Node reference = ref m_Nodes.ElementAt(endNode);
					if (reference.m_CutElementId.m_Version != -2)
					{
						reference.m_CutElementId = identifier;
						labelQueue.Enqueue(endNode);
					}
				}
			}
		}
	}
```

- `private LabelShortages(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private void LabelShortages(ref State state)
	{
		NativeQueue<int> labelQueue = new NativeQueue<int>(Allocator.Temp);
		NodeIndices value = m_NodeIndices.Value;
		Game.Simulation.Flow.Node node = m_Nodes[value.m_SinkNode];
		for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
		{
			Connection connection = m_Connections[i];
			if (connection.m_EndNode != value.m_SourceNode)
			{
				if (m_Nodes[connection.m_EndNode].m_CutElementId.m_Version == -1)
				{
					m_Edges.ElementAt(connection.m_Edge).m_CutElementId = new Identifier(connection.m_EndNode, -1);
				}
				else if (connection.GetIncomingCapacity(m_Edges) > 0 && connection.GetIncomingResidualCapacity(m_Edges) > 0)
				{
					m_Edges.ElementAt(connection.m_Edge).m_CutElementId = new Identifier(connection.m_EndNode, -1);
					LabelShortageSubGraph(ref state, connection.m_EndNode, labelQueue);
				}
			}
		}
		labelQueue.Dispose();
	}
```

- `private LabelShortageSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue) : System.Void`  

```csharp
private void LabelShortageSubGraph(ref State state, int initialNodeIndex, NativeQueue<int> labelQueue)
	{
		NodeIndices value = m_NodeIndices.Value;
		Assert.IsTrue(labelQueue.IsEmpty());
		Identifier identifier = new Identifier(initialNodeIndex, -1);
		Identifier cutElementId = new Identifier(initialNodeIndex, -1);
		m_Nodes.ElementAt(initialNodeIndex).m_CutElementId = identifier;
		labelQueue.Enqueue(initialNodeIndex);
		int item;
		while (labelQueue.TryDequeue(out item))
		{
			state.m_StepCounter++;
			Game.Simulation.Flow.Node node = m_Nodes[item];
			Assert.AreEqual(identifier, node.m_CutElementId);
			for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
			{
				Connection connection = m_Connections[i];
				int endNode = connection.m_EndNode;
				if (connection.GetIncomingCapacity(m_Edges) <= 0)
				{
					continue;
				}
				m_Edges.ElementAt(connection.m_Edge).m_CutElementId = cutElementId;
				if (endNode != value.m_SinkNode && endNode != value.m_SourceNode)
				{
					ref Game.Simulation.Flow.Node reference = ref m_Nodes.ElementAt(endNode);
					if (reference.m_CutElementId.m_Version != -1 && connection.GetIncomingResidualCapacity(m_Edges) > 0)
					{
						reference.m_CutElementId = identifier;
						labelQueue.Enqueue(endNode);
					}
				}
			}
		}
	}
```

- `private LimitImportEdgeCapacity() : System.Void`  

```csharp
private void LimitImportEdgeCapacity()
	{
		NodeIndices value = m_NodeIndices.Value;
		foreach (int tradeNode in m_TradeNodes)
		{
			Game.Simulation.Flow.Node node = m_Nodes[tradeNode];
			for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
			{
				Connection connection = m_Connections[i];
				if (connection.m_EndNode == value.m_SourceNode)
				{
					ref Game.Simulation.Flow.Edge reference = ref m_Edges.ElementAt(connection.m_Edge);
					Assert.IsTrue(reference.flow >= 0);
					reference.m_Capacity = reference.flow;
				}
			}
		}
	}
```

- `private MaxFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.WaterPipeFlowJob+Phase phaseAfterCompletion) : System.Void`  

```csharp
private void MaxFlowPhase(ref State state, int maxSteps, Phase phaseAfterCompletion)
	{
		NativeList<Game.Simulation.Flow.Layer> layers = new NativeList<Game.Simulation.Flow.Layer>(m_LayerStates.Capacity, Allocator.Temp);
		NativeQueue<int> labelQueue = new NativeQueue<int>(Allocator.Temp);
		NativeArray<UnsafeList<int>> activeQueue = new NativeArray<UnsafeList<int>>(m_LayerHeight, Allocator.Temp);
		for (int i = 0; i < m_LayerHeight; i++)
		{
			activeQueue[i] = new UnsafeList<int>(128, Allocator.Temp);
		}
		NodeIndices value = m_NodeIndices.Value;
		MaxFlowSolver maxFlowSolver = new MaxFlowSolver
		{
			m_LayerHeight = m_LayerHeight,
			m_SourceNode = value.m_SourceNode,
			m_SinkNode = value.m_SinkNode,
			m_Nodes = m_Nodes,
			m_Edges = m_Edges,
			m_Connections = m_Connections,
			m_Layers = layers,
			m_LabelQueue = labelQueue,
			m_ActiveQueue = activeQueue,
			m_StepCounter = state.m_StepCounter
		};
		if (m_MaxFlowState.Value.m_CurrentLabelVersion == 0)
		{
			maxFlowSolver.ResetNetwork();
			maxFlowSolver.InitializeState();
		}
		else
		{
			maxFlowSolver.LoadState(m_MaxFlowState, m_LayerStates, m_LayerElements, m_LayerElementRefs);
		}
		while (!maxFlowSolver.m_Complete && (m_FinalFrame || maxFlowSolver.m_StepCounter < maxSteps))
		{
			maxFlowSolver.SolveNextLayer();
		}
		maxFlowSolver.SaveState(m_MaxFlowState, m_LayerStates, m_LayerElements, m_LayerElementRefs);
		foreach (Game.Simulation.Flow.Layer item in layers)
		{
			item.Dispose();
		}
		layers.Dispose();
		foreach (UnsafeList<int> item2 in activeQueue)
		{
			item2.Dispose();
		}
		labelQueue.Dispose();
		activeQueue.Dispose();
		state.m_StepCounter = maxFlowSolver.m_StepCounter;
		if (maxFlowSolver.m_Complete)
		{
			state.m_Phase = phaseAfterCompletion;
		}
	}
```

- `private PostProducerPhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private void PostProducerPhase(ref State state)
	{
		LabelShortages(ref state);
		EnableTradeConnections();
		ResetMaxFlowState();
		state.m_Phase = Phase.Trade;
	}
```

- `private PostTradePhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private void PostTradePhase(ref State state)
	{
		SetTradeConnectionsEnabled(import: true, export: false);
		LabelConnected(ref state);
		LabelShortages(ref state);
		if (m_FluidFlowEnabled)
		{
			FluidFlowSolver.ResetNodes(m_Nodes);
			LimitImportEdgeCapacity();
			PreflowSinkEdges();
			ResetNonSinkEdges();
			m_FluidFlowState.Value = default(FluidFlowSolverState);
			state.m_Phase = Phase.FluidFlow;
		}
		else
		{
			FinalizeFlows();
			state.m_Phase = Phase.Complete;
		}
	}
```

- `private PreflowSinkEdges() : System.Void`  

```csharp
private void PreflowSinkEdges()
	{
		NodeIndices value = m_NodeIndices.Value;
		ref Game.Simulation.Flow.Node reference = ref m_Nodes.ElementAt(value.m_SinkNode);
		for (int i = reference.m_FirstConnection; i < reference.m_LastConnection; i++)
		{
			Connection connection = m_Connections[i];
			ref Game.Simulation.Flow.Edge reference2 = ref m_Edges.ElementAt(connection.m_Edge);
			Assert.IsTrue(reference2.flow >= 0);
			reference2.m_Direction = FlowDirection.None;
			reference2.m_CutElementId = new Identifier(-200, reference2.m_CutElementId.m_Version);
			reference2.FinalizeTempFlow();
			m_Nodes.ElementAt(connection.m_EndNode).m_Excess = reference2.flow;
			reference.m_Excess -= reference2.flow;
		}
	}
```

- `private ResetMaxFlowState() : System.Void`  

```csharp
private void ResetMaxFlowState()
	{
		m_MaxFlowState.Value = default(MaxFlowSolverState);
		m_LayerStates.Length = 0;
		m_LayerElements.Length = 0;
		m_LayerElementRefs.Length = 0;
	}
```

- `private ResetNonSinkEdges() : System.Void`  

```csharp
private void ResetNonSinkEdges()
	{
		for (int i = 0; i < m_Edges.Length; i++)
		{
			ref Game.Simulation.Flow.Edge reference = ref m_Edges.ElementAt(i);
			if (reference.m_CutElementId.m_Index != -200)
			{
				reference.m_FinalFlow = 0;
				reference.m_TempFlow = 0;
			}
		}
	}
```

- `private SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export) : System.Void`  

```csharp
private void SetTradeConnectionsEnabled(bool import, bool export)
	{
		NodeIndices value = m_NodeIndices.Value;
		foreach (int tradeNode in m_TradeNodes)
		{
			Game.Simulation.Flow.Node node = m_Nodes[tradeNode];
			for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
			{
				Connection connection = m_Connections[i];
				ref Game.Simulation.Flow.Edge reference = ref m_Edges.ElementAt(connection.m_Edge);
				if (connection.m_EndNode == value.m_SourceNode)
				{
					Assert.IsTrue(connection.m_Backwards);
					reference.m_Capacity = (import ? m_ImportCapacity : 0);
				}
				else if (connection.m_EndNode == value.m_SinkNode)
				{
					Assert.IsFalse(connection.m_Backwards);
					reference.m_Capacity = (export ? m_ExportCapacity : 0);
				}
			}
		}
	}
```


## Nested types

- `Game.Simulation.WaterPipeFlowJob+Phase`  
- `Game.Simulation.WaterPipeFlowJob+State`  
- `Game.Simulation.WaterPipeFlowJob+Data`  

