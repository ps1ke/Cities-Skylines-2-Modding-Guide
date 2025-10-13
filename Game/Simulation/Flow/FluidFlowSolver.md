# Game.Simulation.Flow.FluidFlowSolver

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct FluidFlowSolver
{
    public System.Int32 m_SourceNode;
    public System.Int32 m_SinkNode;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections;
    public Colossal.Collections.NativeMinHeap<Game.Simulation.Flow.LabelHeapData> m_LabelQueue;
    public Colossal.Collections.NativeMinHeap<Game.Simulation.Flow.PushHeapData> m_PushQueue;
    public System.Boolean m_Complete;
    public System.Int32 m_CurrentVersion;
    public System.Int32 m_StepCounter;

    private System.Void AugmentOutgoingFinalFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow);
    private Game.Simulation.Flow.Connection GetConnection(System.Int32 index);
    private Game.Simulation.Flow.Edge& GetEdge(System.Int32 index);
    private System.Int32 GetLength(Game.Simulation.Flow.Connection connection);
    private System.Int32 GetMaxAdditionalOutgoingFlow(Game.Simulation.Flow.Connection connection);
    private Game.Simulation.Flow.Node& GetNode(System.Int32 index);
    public System.Void InitializeState();
    private System.Void Label();
    public System.Void LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState);
    public System.Void Preflow();
    private System.Void Push();
    public System.Void ResetFlows();
    public static System.Void ResetFlows(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges);
    public System.Void ResetNodes();
    public static System.Void ResetNodes(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes);
    public System.Void SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState);
    public System.Void Solve();
    public System.Void SolveStep();
}
```


## Fields

- `public System.Int32 m_SourceNode`  

```csharp
public System.Int32 m_SourceNode;
```

- `public System.Int32 m_SinkNode`  

```csharp
public System.Int32 m_SinkNode;
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

- `public Colossal.Collections.NativeMinHeap<Game.Simulation.Flow.LabelHeapData> m_LabelQueue`  

```csharp
public Colossal.Collections.NativeMinHeap<Game.Simulation.Flow.LabelHeapData> m_LabelQueue;
```

- `public Colossal.Collections.NativeMinHeap<Game.Simulation.Flow.PushHeapData> m_PushQueue`  

```csharp
public Colossal.Collections.NativeMinHeap<Game.Simulation.Flow.PushHeapData> m_PushQueue;
```

- `public System.Boolean m_Complete`  

```csharp
public System.Boolean m_Complete;
```

- `public System.Int32 m_CurrentVersion`  

```csharp
public System.Int32 m_CurrentVersion;
```

- `public System.Int32 m_StepCounter`  

```csharp
public System.Int32 m_StepCounter;
```


## Methods

- `private AugmentOutgoingFinalFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow) : System.Void`  

```csharp
private void AugmentOutgoingFinalFlow(in Connection connection, int flow)
	{
		Assert.IsTrue(flow >= 0);
		ref Node node = ref GetNode(connection.m_StartNode);
		ref Node node2 = ref GetNode(connection.m_EndNode);
		ref Edge edge = ref GetEdge(connection.m_Edge);
		node.m_Excess += flow;
		edge.m_FinalFlow += (connection.m_Backwards ? (-flow) : flow);
		node2.m_Excess -= flow;
		int finalFlow = edge.m_FinalFlow;
		Assert.IsFalse(finalFlow < -edge.GetCapacity(backwards: true));
		Assert.IsFalse(finalFlow > edge.GetCapacity(backwards: false));
	}
```

- `private GetConnection(System.Int32 index) : Game.Simulation.Flow.Connection`  

```csharp
private Connection GetConnection(int index)
	{
		return m_Connections[index];
	}
```

- `private GetEdge(System.Int32 index) : Game.Simulation.Flow.Edge&`  

```csharp
private ref Edge GetEdge(int index)
	{
		return ref m_Edges.ElementAt(index);
	}
```

- `private GetLength(Game.Simulation.Flow.Connection connection) : System.Int32`  

```csharp
private int GetLength(Connection connection)
	{
		int outgoingFinalFlow = connection.GetOutgoingFinalFlow(m_Edges);
		if (outgoingFinalFlow > 1)
		{
			return 1 + math.ceillog2(outgoingFinalFlow);
		}
		if (outgoingFinalFlow < -1)
		{
			return 1 - math.ceillog2(-outgoingFinalFlow);
		}
		return 1;
	}
```

- `private GetMaxAdditionalOutgoingFlow(Game.Simulation.Flow.Connection connection) : System.Int32`  

```csharp
private int GetMaxAdditionalOutgoingFlow(Connection connection)
	{
		int outgoingFinalFlow = connection.GetOutgoingFinalFlow(m_Edges);
		int outgoingResidualCapacity = connection.GetOutgoingResidualCapacity(m_Edges);
		int num = ((outgoingFinalFlow > 1) ? (Mathf.NextPowerOfTwo(outgoingFinalFlow) << 1) : ((outgoingFinalFlow < -2) ? (-(Mathf.NextPowerOfTwo(-outgoingFinalFlow) >> 2) - 1) : ((outgoingFinalFlow == -2) ? 1 : 2)));
		return math.min(num - outgoingFinalFlow, outgoingResidualCapacity);
	}
```

- `private GetNode(System.Int32 index) : Game.Simulation.Flow.Node&`  

```csharp
private ref Node GetNode(int index)
	{
		return ref m_Nodes.ElementAt(index);
	}
```

- `public InitializeState() : System.Void`  

```csharp
public void InitializeState()
	{
		m_Complete = false;
		m_CurrentVersion = 0;
	}
```

- `private Label() : System.Void`  

```csharp
private void Label()
	{
		Assert.AreEqual(0, m_LabelQueue.Length);
		Assert.AreEqual(0, m_PushQueue.Length);
		ref Node node = ref GetNode(m_SourceNode);
		node.m_Distance = 0;
		node.m_Height = 0;
		node.m_Version = m_CurrentVersion;
		node.m_Enqueued = true;
		m_LabelQueue.Insert(new LabelHeapData(m_SourceNode, 0));
		while (m_LabelQueue.Length != 0)
		{
			LabelHeapData labelHeapData = m_LabelQueue.Extract();
			ref Node node2 = ref GetNode(labelHeapData.m_NodeIndex);
			if (node2.m_Distance < labelHeapData.m_Distance)
			{
				continue;
			}
			m_StepCounter++;
			Assert.IsTrue(node2.m_Distance == labelHeapData.m_Distance);
			int num = node2.m_Height + 1;
			for (int i = node2.m_FirstConnection; i < node2.m_LastConnection; i++)
			{
				Connection connection = GetConnection(i);
				if (connection.GetOutgoingResidualCapacity(m_Edges) > 0)
				{
					Assert.IsTrue(connection.m_EndNode != m_SinkNode);
					ref Node node3 = ref GetNode(connection.m_EndNode);
					int num2 = node2.m_Distance + GetLength(connection);
					if (node3.m_Version != m_CurrentVersion)
					{
						node3.m_Enqueued = false;
						node3.m_Height = num;
						node3.m_Version = m_CurrentVersion;
						node3.m_Distance = num2;
						node3.m_Predecessor = i;
						m_LabelQueue.Insert(new LabelHeapData(connection.m_EndNode, num2));
					}
					else if (node3.m_Distance > num2)
					{
						node3.m_Enqueued &= node3.m_Height == num;
						node3.m_Height = num;
						node3.m_Distance = num2;
						node3.m_Predecessor = i;
						m_LabelQueue.Insert(new LabelHeapData(connection.m_EndNode, num2));
					}
				}
			}
			if (!node2.m_Enqueued && node2.m_Excess > 0)
			{
				node2.m_Enqueued = true;
				m_PushQueue.Insert(new PushHeapData(labelHeapData.m_NodeIndex, node2.m_Height));
			}
		}
	}
```

- `public LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState) : System.Void`  

```csharp
public void LoadState(NativeReference<FluidFlowSolverState> solverState)
	{
		FluidFlowSolverState value = solverState.Value;
		m_Complete = value.m_Complete;
		m_CurrentVersion = value.m_CurrentVersion;
	}
```

- `public Preflow() : System.Void`  

```csharp
public void Preflow()
	{
		Node node = GetNode(m_SinkNode);
		for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
		{
			Connection connection = GetConnection(i);
			int incomingResidualCapacity = connection.GetIncomingResidualCapacity(m_Edges);
			if (incomingResidualCapacity > 0)
			{
				AugmentOutgoingFinalFlow(connection.Reverse(), incomingResidualCapacity);
			}
		}
	}
```

- `private Push() : System.Void`  

```csharp
private void Push()
	{
		Assert.AreEqual(0, m_LabelQueue.Length);
		Assert.AreNotEqual(0, m_PushQueue.Length);
		while (m_PushQueue.Length != 0)
		{
			PushHeapData pushHeapData = m_PushQueue.Extract();
			ref Node node = ref GetNode(pushHeapData.m_NodeIndex);
			if (node.m_Enqueued && pushHeapData.m_Height == node.m_Height)
			{
				m_StepCounter++;
				Assert.IsTrue(node.m_Excess > 0);
				Assert.AreNotEqual(0, node.m_Predecessor);
				node.m_Enqueued = false;
				Connection connection = GetConnection(node.m_Predecessor);
				Assert.IsTrue(connection.GetOutgoingResidualCapacity(m_Edges) > 0);
				Assert.IsTrue(connection.m_EndNode == pushHeapData.m_NodeIndex);
				int num = math.min(node.m_Excess, GetMaxAdditionalOutgoingFlow(connection));
				Assert.IsTrue(num > 0);
				ref Node node2 = ref GetNode(connection.m_StartNode);
				if (!node2.m_Enqueued)
				{
					node2.m_Enqueued = true;
					m_PushQueue.Insert(new PushHeapData(connection.m_StartNode, node2.m_Height));
				}
				AugmentOutgoingFinalFlow(in connection, num);
			}
		}
	}
```

- `public ResetFlows() : System.Void`  

```csharp
public static void ResetFlows(NativeArray<Edge> edges)
	{
		for (int i = 0; i < edges.Length; i++)
		{
			ref Edge reference = ref edges.ElementAt(i);
			reference.m_FinalFlow = 0;
			reference.m_TempFlow = 0;
		}
	}
```

- `public static ResetFlows(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Void`  

```csharp
public static void ResetFlows(NativeArray<Edge> edges)
	{
		for (int i = 0; i < edges.Length; i++)
		{
			ref Edge reference = ref edges.ElementAt(i);
			reference.m_FinalFlow = 0;
			reference.m_TempFlow = 0;
		}
	}
```

- `public ResetNodes() : System.Void`  

```csharp
public static void ResetNodes(NativeArray<Node> nodes)
	{
		for (int i = 0; i < nodes.Length; i++)
		{
			ref Node reference = ref nodes.ElementAt(i);
			reference.m_Height = 0;
			reference.m_Excess = 0;
			reference.m_Version = 0;
			reference.m_Distance = 0;
			reference.m_Predecessor = 0;
			reference.m_Enqueued = false;
		}
	}
```

- `public static ResetNodes(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes) : System.Void`  

```csharp
public static void ResetNodes(NativeArray<Node> nodes)
	{
		for (int i = 0; i < nodes.Length; i++)
		{
			ref Node reference = ref nodes.ElementAt(i);
			reference.m_Height = 0;
			reference.m_Excess = 0;
			reference.m_Version = 0;
			reference.m_Distance = 0;
			reference.m_Predecessor = 0;
			reference.m_Enqueued = false;
		}
	}
```

- `public SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState) : System.Void`  

```csharp
public void SaveState(NativeReference<FluidFlowSolverState> solverState)
	{
		solverState.Value = new FluidFlowSolverState
		{
			m_Complete = m_Complete,
			m_CurrentVersion = m_CurrentVersion
		};
	}
```

- `public Solve() : System.Void`  

```csharp
public void Solve()
	{
		while (!m_Complete)
		{
			SolveStep();
		}
	}
```

- `public SolveStep() : System.Void`  

```csharp
public void SolveStep()
	{
		m_CurrentVersion++;
		Label();
		if (m_PushQueue.Length != 0)
		{
			Push();
		}
		else
		{
			m_Complete = true;
		}
	}
```


