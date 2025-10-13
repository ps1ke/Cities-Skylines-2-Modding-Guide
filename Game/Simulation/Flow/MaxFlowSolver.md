# Game.Simulation.Flow.MaxFlowSolver

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct MaxFlowSolver
{
    public System.Int32 m_LayerHeight;
    public System.Int32 m_SourceNode;
    public System.Int32 m_SinkNode;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections;
    public Unity.Collections.NativeList<Game.Simulation.Flow.Layer> m_Layers;
    public Unity.Collections.NativeQueue<System.Int32> m_LabelQueue;
    public Unity.Collections.NativeArray<Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32>> m_ActiveQueue;
    public System.Boolean m_Complete;
    public System.Int32 m_CurrentLayerIndex;
    public System.Int32 m_NextLayerIndex;
    public System.Int32 m_CurrentLabelVersion;
    public System.Int32 m_CurrentActiveVersion;
    public System.Int32 m_StepCounter;
    public static const System.Int32 kMaxNodes;

    private System.Void AddAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection);
    private System.Void AddInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection);
    private System.Void AdvanceActiveLayer(System.Int32 activeLayerIndex, System.Int32& retreatLayerIndex);
    private System.Int32 AdvanceToSource();
    private System.Void AugmentIncomingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow);
    private System.Void AugmentOutgoingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow);
    private System.Void BumpAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection);
    private System.Void BumpInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection);
    private System.Void CreateElementLink(System.Int32 lowerLayerIndex, System.Int32 lowerElementIndex, System.Int32 higherLayerIndex, System.Int32 higherElementIndex);
    private System.Void DeleteLinkedElements(System.Int32 lowerLayerIndex, System.Int32 index);
    private System.Void FinalizeTempFlow(Game.Simulation.Flow.Connection& connection);
    private Game.Simulation.Flow.Connection GetConnection(System.Int32 index);
    private Game.Simulation.Flow.Edge& GetEdge(System.Int32 index);
    private Game.Simulation.Flow.Layer& GetLayer(System.Int32 index);
    private System.Int32 GetLayerIndexForHeight(System.Int32 height);
    private System.Int32 GetLowerCutHeight(System.Int32 layerIndex);
    private Game.Simulation.Flow.Node& GetNode(System.Int32 index);
    private System.Int32 GetNodeValidLayerIndex(Game.Simulation.Flow.Node node);
    private System.Int32 GetOutgoingTempFlow(Game.Simulation.Flow.Connection& connection);
    private System.Void GetTotalAdvancedFlow(Game.Simulation.Flow.Node currentNode, System.Int32 heightPlusOne, System.Int32& branchFlow, System.Int32& sinkFlow, Game.Simulation.Flow.Connection& sinkConnection);
    private System.Int32 GetUpperCutHeight(System.Int32 layerIndex);
    public System.Void InitializeState();
    private System.Boolean LabelPreflow();
    public System.Void LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs);
    public System.Void ResetNetwork();
    public static System.Void ResetNetwork(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes, Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges, System.Int32 sourceNode);
    private System.Void RetreatActiveLayer(System.Int32 activeLayerIndex);
    private System.Void RetreatFromLayer(System.Int32 retreatLayerIndex);
    public System.Void SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs);
    public System.Void Solve();
    public System.Void SolveNextLayer();
}
```


## Fields

- `public System.Int32 m_LayerHeight`  

```csharp
public System.Int32 m_LayerHeight;
```

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

- `public Unity.Collections.NativeList<Game.Simulation.Flow.Layer> m_Layers`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.Flow.Layer> m_Layers;
```

- `public Unity.Collections.NativeQueue<System.Int32> m_LabelQueue`  

```csharp
public Unity.Collections.NativeQueue<System.Int32> m_LabelQueue;
```

- `public Unity.Collections.NativeArray<Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32>> m_ActiveQueue`  

```csharp
public Unity.Collections.NativeArray<Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32>> m_ActiveQueue;
```

- `public System.Boolean m_Complete`  

```csharp
public System.Boolean m_Complete;
```

- `public System.Int32 m_CurrentLayerIndex`  

```csharp
public System.Int32 m_CurrentLayerIndex;
```

- `public System.Int32 m_NextLayerIndex`  

```csharp
public System.Int32 m_NextLayerIndex;
```

- `public System.Int32 m_CurrentLabelVersion`  

```csharp
public System.Int32 m_CurrentLabelVersion;
```

- `public System.Int32 m_CurrentActiveVersion`  

```csharp
public System.Int32 m_CurrentActiveVersion;
```

- `public System.Int32 m_StepCounter`  

```csharp
public System.Int32 m_StepCounter;
```

- `public static const System.Int32 kMaxNodes`  

```csharp
public static const System.Int32 kMaxNodes;
```


## Methods

- `private AddAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  

```csharp
private void AddAdmissibleLayerCutElement(int lowerLayerIndex, int higherLayerIndex, in Connection lhConnection)
	{
		ref Layer layer = ref GetLayer(higherLayerIndex);
		CutElement element = new CutElement
		{
			m_Flags = (CutElementFlags.Created | CutElementFlags.Admissible | CutElementFlags.Changed),
			m_StartNode = lhConnection.m_StartNode,
			m_EndNode = lhConnection.m_EndNode,
			m_Edge = lhConnection.m_Edge,
			m_Version = m_CurrentLabelVersion,
			m_LinkedElements = -1,
			m_NextIndex = -1
		};
		int num = layer.AddCutElement(in element);
		layer.GetCutElement(num).m_Group = num;
		GetEdge(lhConnection.m_Edge).m_CutElementId = new Identifier(num, m_CurrentLabelVersion);
		int index = GetNode(lhConnection.m_StartNode).m_CutElementId.m_Index;
		CreateElementLink(lowerLayerIndex, index, higherLayerIndex, num);
	}
```

- `private AddInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  

```csharp
private void AddInadmissibleLayerCutElement(int lowerLayerIndex, int higherLayerIndex, in Connection lhConnection)
	{
		ref Layer layer = ref GetLayer(higherLayerIndex);
		int index = GetNode(lhConnection.m_EndNode).m_CutElementId.m_Index;
		ref CutElement cutElement = ref layer.GetCutElement(index);
		CutElement element = new CutElement
		{
			m_Flags = CutElementFlags.Created,
			m_StartNode = lhConnection.m_StartNode,
			m_EndNode = lhConnection.m_EndNode,
			m_Edge = lhConnection.m_Edge,
			m_Group = cutElement.m_Group,
			m_Version = m_CurrentLabelVersion,
			m_LinkedElements = -1,
			m_NextIndex = cutElement.m_NextIndex
		};
		int num = layer.AddCutElement(in element);
		layer.GetCutElement(index).m_NextIndex = num;
		GetEdge(lhConnection.m_Edge).m_CutElementId = new Identifier(num, m_CurrentLabelVersion);
		int index2 = GetNode(lhConnection.m_StartNode).m_CutElementId.m_Index;
		CreateElementLink(lowerLayerIndex, index2, higherLayerIndex, num);
	}
```

- `private AdvanceActiveLayer(System.Int32 activeLayerIndex, System.Int32& retreatLayerIndex) : System.Void`  

```csharp
private void AdvanceActiveLayer(int activeLayerIndex, ref int retreatLayerIndex)
	{
		bool flag = activeLayerIndex == m_CurrentLayerIndex;
		for (int num = m_LayerHeight - 1; num >= 0; num--)
		{
			bool flag2 = num == 0;
			ref UnsafeList<int> reference = ref m_ActiveQueue.ElementAt(num);
			for (int i = 0; i < reference.Length; i++)
			{
				m_StepCounter++;
				int num2 = reference[i];
				ref Node node = ref GetNode(num2);
				Assert.AreEqual(m_CurrentActiveVersion, node.m_Version);
				Assert.AreNotEqual(m_SourceNode, num2);
				Assert.AreNotEqual(m_SinkNode, num2);
				Assert.IsFalse(node.m_Excess <= 0);
				int num3 = node.m_Height - 1;
				Assert.AreEqual(GetLowerCutHeight(activeLayerIndex) + num - 1, num3);
				bool condition = false;
				bool flag3 = false;
				for (int j = node.m_FirstConnection; j < node.m_LastConnection; j++)
				{
					Connection connection = GetConnection(j);
					int value = connection.m_EndNode;
					ref Node node2 = ref GetNode(value);
					if (!flag && node2.m_Version != m_CurrentActiveVersion)
					{
						node2.m_Retreat = false;
						FinalizeTempFlow(in connection);
					}
					if (node2.m_Height == num3)
					{
						int incomingResidualCapacity = connection.GetIncomingResidualCapacity(m_Edges);
						int num4 = math.min(incomingResidualCapacity, node.m_Excess);
						if (num4 != 0)
						{
							if (node2.m_Version != m_CurrentActiveVersion)
							{
								node2.m_Retreat = false;
								node2.m_Version = m_CurrentActiveVersion;
								int index = (flag2 ? (m_LayerHeight - 1) : (num - 1));
								m_ActiveQueue.ElementAt(index).Add(in value);
							}
							FinalizeTempFlow(in connection);
							AugmentIncomingTempFlow(in connection, num4);
							condition = true;
							if (node.m_Retreat)
							{
								node2.m_Retreat = true;
							}
							if (num4 != incomingResidualCapacity)
							{
								Assert.IsTrue(connection.GetIncomingResidualCapacity(m_Edges) > 0);
								flag3 = true;
							}
							else
							{
								Assert.AreEqual(0, connection.GetIncomingResidualCapacity(m_Edges));
							}
						}
					}
					if (flag && flag3 && node.m_Excess == 0)
					{
						break;
					}
					Assert.IsFalse(node.m_Excess < 0);
				}
				Assert.IsTrue(condition);
				if (!flag3)
				{
					bool flag4 = node.m_Excess != 0;
					if (num3 > 0)
					{
						m_NextLayerIndex = GetLayerIndexForHeight(num3);
						Layer layer = GetLayer(m_NextLayerIndex);
						if (flag4)
						{
							retreatLayerIndex = activeLayerIndex;
						}
						for (int k = node.m_FirstConnection; k < node.m_LastConnection; k++)
						{
							ref Node node3 = ref GetNode(GetConnection(k).m_EndNode);
							if (node3.m_Height == num3)
							{
								layer.GetCutElement(node3.m_CutElementId.m_Index).isChanged = true;
								if (flag4)
								{
									node3.m_Retreat = true;
								}
							}
						}
					}
					else
					{
						m_NextLayerIndex = 0;
						Layer layer2 = GetLayer(m_NextLayerIndex);
						if (flag4)
						{
							retreatLayerIndex = 0;
						}
						layer2.GetCutElement(node.m_CutElementId.m_Index).isDeleted = true;
					}
				}
				else
				{
					Assert.AreEqual(0, node.m_Excess);
				}
			}
			reference.Clear();
		}
	}
```

- `private AdvanceToSource() : System.Int32`  

```csharp
private int AdvanceToSource()
	{
		int retreatLayerIndex = m_CurrentLayerIndex + 1;
		for (int num = m_CurrentLayerIndex; num >= 0; num--)
		{
			AdvanceActiveLayer(num, ref retreatLayerIndex);
		}
		ref UnsafeList<int> reference = ref m_ActiveQueue.ElementAt(m_LayerHeight - 1);
		Assert.AreEqual(1, reference.Length);
		Assert.AreEqual(m_SourceNode, reference[0]);
		reference.Clear();
		ref Node node = ref GetNode(m_SourceNode);
		node.m_Retreat = false;
		node.m_Version = m_CurrentActiveVersion;
		if (m_NextLayerIndex <= m_CurrentLayerIndex)
		{
			m_CurrentLabelVersion++;
		}
		return retreatLayerIndex;
	}
```

- `private AugmentIncomingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow) : System.Void`  

```csharp
private void AugmentIncomingTempFlow(in Connection connection, int flow)
	{
		Assert.IsTrue(flow >= 0);
		ref Node node = ref GetNode(connection.m_StartNode);
		ref Node node2 = ref GetNode(connection.m_EndNode);
		ref Edge edge = ref GetEdge(connection.m_Edge);
		node2.m_Excess += flow;
		edge.m_TempFlow += (connection.m_Backwards ? flow : (-flow));
		node.m_Excess -= flow;
		int flow2 = edge.flow;
		Assert.IsTrue(connection.m_EndNode == m_SinkNode || node2.m_Excess >= 0);
		Assert.IsTrue(connection.m_StartNode == m_SinkNode || node.m_Excess >= 0);
		Assert.IsFalse(flow2 < -edge.GetCapacity(backwards: true));
		Assert.IsFalse(flow2 > edge.GetCapacity(backwards: false));
	}
```

- `private AugmentOutgoingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow) : System.Void`  

```csharp
private void AugmentOutgoingTempFlow(in Connection connection, int flow)
	{
		Assert.IsTrue(flow >= 0);
		ref Node node = ref GetNode(connection.m_StartNode);
		ref Node node2 = ref GetNode(connection.m_EndNode);
		ref Edge edge = ref GetEdge(connection.m_Edge);
		node.m_Excess += flow;
		edge.m_TempFlow += (connection.m_Backwards ? (-flow) : flow);
		node2.m_Excess -= flow;
		int flow2 = edge.flow;
		Assert.IsTrue(connection.m_StartNode == m_SinkNode || node.m_Excess >= 0);
		Assert.IsTrue(connection.m_EndNode == m_SinkNode || node2.m_Excess >= 0);
		Assert.IsFalse(flow2 < -edge.GetCapacity(backwards: true));
		Assert.IsFalse(flow2 > edge.GetCapacity(backwards: false));
	}
```

- `private BumpAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  

```csharp
private void BumpAdmissibleLayerCutElement(int lowerLayerIndex, int higherLayerIndex, in Connection lhConnection)
	{
		Layer layer = GetLayer(higherLayerIndex);
		int index = GetEdge(lhConnection.m_Edge).m_CutElementId.m_Index;
		layer.GetCutElement(index).isDeleted = false;
		int index2 = GetNode(lhConnection.m_StartNode).m_CutElementId.m_Index;
		CreateElementLink(lowerLayerIndex, index2, higherLayerIndex, index);
	}
```

- `private BumpInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  

```csharp
private void BumpInadmissibleLayerCutElement(int lowerLayerIndex, int higherLayerIndex, in Connection lhConnection)
	{
		Layer layer = GetLayer(higherLayerIndex);
		int index = GetEdge(lhConnection.m_Edge).m_CutElementId.m_Index;
		ref CutElement cutElement = ref layer.GetCutElement(index);
		cutElement.isDeleted = false;
		if (cutElement.isAdmissible)
		{
			cutElement.isAdmissible = false;
			cutElement.isChanged = true;
		}
		int index2 = GetNode(lhConnection.m_StartNode).m_CutElementId.m_Index;
		CreateElementLink(lowerLayerIndex, index2, higherLayerIndex, index);
	}
```

- `private CreateElementLink(System.Int32 lowerLayerIndex, System.Int32 lowerElementIndex, System.Int32 higherLayerIndex, System.Int32 higherElementIndex) : System.Void`  

```csharp
private void CreateElementLink(int lowerLayerIndex, int lowerElementIndex, int higherLayerIndex, int higherElementIndex)
	{
		ref Layer layer = ref GetLayer(lowerLayerIndex);
		ref CutElement cutElement = ref layer.GetCutElement(lowerElementIndex);
		CutElementRef elementRef = new CutElementRef
		{
			m_Layer = higherLayerIndex,
			m_Index = higherElementIndex,
			m_NextIndex = cutElement.m_LinkedElements
		};
		int linkedElements = layer.AddCutElementRef(in elementRef);
		cutElement.m_LinkedElements = linkedElements;
	}
```

- `private DeleteLinkedElements(System.Int32 lowerLayerIndex, System.Int32 index) : System.Void`  

```csharp
private void DeleteLinkedElements(int lowerLayerIndex, int index)
	{
		ref Layer layer = ref GetLayer(lowerLayerIndex);
		ref CutElement cutElement = ref layer.GetCutElement(index);
		int num = cutElement.m_LinkedElements;
		cutElement.m_LinkedElements = -1;
		while (num != -1)
		{
			CutElementRef cutElementRef = layer.GetCutElementRef(num);
			Layer layer2 = GetLayer(cutElementRef.m_Layer);
			layer2.GetCutElement(cutElementRef.m_Index).isDeleted = true;
			int nextIndex = cutElementRef.m_NextIndex;
			layer.FreeCutElementRef(num);
			num = nextIndex;
		}
	}
```

- `private FinalizeTempFlow(Game.Simulation.Flow.Connection& connection) : System.Void`  

```csharp
private void FinalizeTempFlow(in Connection connection)
	{
		GetEdge(connection.m_Edge).FinalizeTempFlow();
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

- `private GetLayer(System.Int32 index) : Game.Simulation.Flow.Layer&`  

```csharp
private ref Layer GetLayer(int index)
	{
		return ref m_Layers.ElementAt(index);
	}
```

- `private GetLayerIndexForHeight(System.Int32 height) : System.Int32`  

```csharp
private int GetLayerIndexForHeight(int height)
	{
		return (height - 1) / m_LayerHeight;
	}
```

- `private GetLowerCutHeight(System.Int32 layerIndex) : System.Int32`  

```csharp
private int GetLowerCutHeight(int layerIndex)
	{
		return layerIndex * m_LayerHeight + 1;
	}
```

- `private GetNode(System.Int32 index) : Game.Simulation.Flow.Node&`  

```csharp
private ref Node GetNode(int index)
	{
		return ref m_Nodes.ElementAt(index);
	}
```

- `private GetNodeValidLayerIndex(Game.Simulation.Flow.Node node) : System.Int32`  

```csharp
private int GetNodeValidLayerIndex(Node node)
	{
		if (node.m_Height != 16777216 && node.m_CutElementId.m_Version != 0)
		{
			int layerIndexForHeight = GetLayerIndexForHeight(node.m_Height);
			Layer layer = GetLayer(layerIndexForHeight);
			if (layer.ContainsCutElement(node.m_CutElementId))
			{
				return layerIndexForHeight;
			}
		}
		return -1;
	}
```

- `private GetOutgoingTempFlow(Game.Simulation.Flow.Connection& connection) : System.Int32`  

```csharp
private int GetOutgoingTempFlow(in Connection connection)
	{
		Edge edge = GetEdge(connection.m_Edge);
		if (!connection.m_Backwards)
		{
			return edge.m_TempFlow;
		}
		return -edge.m_TempFlow;
	}
```

- `private GetTotalAdvancedFlow(Game.Simulation.Flow.Node currentNode, System.Int32 heightPlusOne, System.Int32& branchFlow, System.Int32& sinkFlow, Game.Simulation.Flow.Connection& sinkConnection) : System.Void`  

```csharp
private void GetTotalAdvancedFlow(Node currentNode, int heightPlusOne, out int branchFlow, out int sinkFlow, out Connection sinkConnection)
	{
		sinkConnection = default(Connection);
		branchFlow = 0;
		sinkFlow = 0;
		for (int i = currentNode.m_FirstConnection; i < currentNode.m_LastConnection; i++)
		{
			Connection connection = GetConnection(i);
			if (connection.m_EndNode == m_SinkNode)
			{
				int outgoingTempFlow = GetOutgoingTempFlow(in connection);
				Assert.IsFalse(outgoingTempFlow < 0);
				Assert.IsTrue(sinkFlow == 0);
				sinkFlow = outgoingTempFlow;
				sinkConnection = connection;
			}
			else if (GetNode(connection.m_EndNode).m_Height == heightPlusOne)
			{
				int outgoingTempFlow2 = GetOutgoingTempFlow(in connection);
				Assert.IsFalse(outgoingTempFlow2 < 0);
				branchFlow += outgoingTempFlow2;
			}
		}
	}
```

- `private GetUpperCutHeight(System.Int32 layerIndex) : System.Int32`  

```csharp
private int GetUpperCutHeight(int layerIndex)
	{
		return (layerIndex + 1) * m_LayerHeight;
	}
```

- `public InitializeState() : System.Void`  

```csharp
public void InitializeState()
	{
		m_Complete = false;
		m_NextLayerIndex = 0;
		m_CurrentLabelVersion = 1;
		m_CurrentActiveVersion = 1;
		Node node = GetNode(m_SourceNode);
		Layer value = new Layer(node.connectionCount, Allocator.Temp);
		for (int i = node.m_FirstConnection; i < node.m_LastConnection; i++)
		{
			Connection connection = GetConnection(i);
			if (connection.GetOutgoingResidualCapacity(m_Edges) > 0)
			{
				CutElement element = new CutElement
				{
					m_Flags = (CutElementFlags.Created | CutElementFlags.Admissible | CutElementFlags.Changed),
					m_StartNode = connection.m_StartNode,
					m_EndNode = connection.m_EndNode,
					m_Edge = connection.m_Edge,
					m_Version = m_CurrentLabelVersion,
					m_LinkedElements = -1,
					m_NextIndex = -1
				};
				int num = value.AddCutElement(in element);
				value.GetCutElement(num).m_Group = num;
				GetEdge(connection.m_Edge).m_CutElementId = new Identifier(num, m_CurrentLabelVersion);
			}
		}
		m_Layers.Clear();
		m_Layers.Add(in value);
	}
```

- `private LabelPreflow() : System.Boolean`  

```csharp
private bool LabelPreflow()
	{
		bool result = false;
		ref Layer layer = ref GetLayer(m_CurrentLayerIndex);
		int num = m_CurrentLayerIndex + 1;
		Layer layer2 = GetLayer(num);
		int lowerCutHeight = GetLowerCutHeight(m_CurrentLayerIndex);
		int upperCutHeight = GetUpperCutHeight(m_CurrentLayerIndex);
		for (int i = 0; i < layer.m_Elements.Length; i++)
		{
			CutElement cutElement = layer.GetCutElement(i);
			if (!cutElement.isCreated || (!cutElement.isChanged && !cutElement.isDeleted))
			{
				continue;
			}
			int num2 = cutElement.m_Group;
			do
			{
				ref CutElement cutElement2 = ref layer.GetCutElement(num2);
				int nextIndex = cutElement2.m_NextIndex;
				DeleteLinkedElements(m_CurrentLayerIndex, num2);
				if (cutElement2.isDeleted)
				{
					layer.FreeCutElement(num2);
				}
				else if (!cutElement2.isAdmissible)
				{
					Node node = GetNode(cutElement2.m_StartNode);
					int layerIndexForHeight = GetLayerIndexForHeight(node.m_Height);
					Assert.IsTrue(layerIndexForHeight < m_CurrentLayerIndex);
					ref Layer layer3 = ref GetLayer(layerIndexForHeight);
					layer.FreeCutElement(num2);
					layer3.RemoveElementLink(node.m_CutElementId.m_Index, m_CurrentLayerIndex, num2);
				}
				else
				{
					Identifier cutElementId = new Identifier(num2, m_CurrentLabelVersion);
					cutElement2.m_Group = num2;
					cutElement2.m_Version = m_CurrentLabelVersion;
					GetEdge(cutElement2.m_Edge).m_CutElementId = cutElementId;
					cutElement2.isChanged = false;
					cutElement2.m_NextIndex = -1;
					ref Node node2 = ref GetNode(cutElement2.m_EndNode);
					if (node2.m_CutElementId.m_Version != m_CurrentLabelVersion)
					{
						node2.m_Height = lowerCutHeight;
						node2.m_CutElementId = cutElementId;
						m_LabelQueue.Enqueue(cutElement2.m_EndNode);
					}
					else
					{
						layer.MergeGroups(node2.m_CutElementId.m_Index, num2);
					}
				}
				num2 = nextIndex;
			}
			while (num2 != -1);
		}
		int item;
		while (m_LabelQueue.TryDequeue(out item))
		{
			m_StepCounter++;
			ref Node node3 = ref GetNode(item);
			for (int j = node3.m_FirstConnection; j < node3.m_LastConnection; j++)
			{
				Connection connection = GetConnection(j);
				ref Edge edge = ref GetEdge(connection.m_Edge);
				int endNode = connection.m_EndNode;
				edge.FinalizeTempFlow();
				if (endNode != m_SinkNode)
				{
					if (endNode == m_SourceNode)
					{
						continue;
					}
					ref Node node4 = ref GetNode(endNode);
					int nodeValidLayerIndex = GetNodeValidLayerIndex(node4);
					if (nodeValidLayerIndex == -1)
					{
						if (connection.GetOutgoingResidualCapacity(m_Edges) > 0)
						{
							if (node3.m_Height != upperCutHeight)
							{
								edge.m_CutElementId = node3.m_CutElementId;
								node4.m_Height = node3.m_Height + 1;
								node4.m_CutElementId = node3.m_CutElementId;
								node4.m_Retreat = false;
								m_LabelQueue.Enqueue(endNode);
							}
							else
							{
								node4.m_Height = node3.m_Height + 1;
								node4.m_CutElementId = default(Identifier);
								if (layer2.ContainsCutElementForConnection(edge.m_CutElementId, connection, admissible: true))
								{
									BumpAdmissibleLayerCutElement(m_CurrentLayerIndex, num, in connection);
								}
								else
								{
									AddAdmissibleLayerCutElement(m_CurrentLayerIndex, num, in connection);
								}
							}
						}
						else
						{
							node4.m_Height = 16777216;
							node4.m_CutElementId = default(Identifier);
						}
					}
					else if (nodeValidLayerIndex == m_CurrentLayerIndex)
					{
						if (!node4.m_CutElementId.Equals(node3.m_CutElementId))
						{
							layer.MergeGroups(node4.m_CutElementId.m_Index, node3.m_CutElementId.m_Index);
						}
					}
					else if (nodeValidLayerIndex < m_CurrentLayerIndex)
					{
						if (connection.GetOutgoingResidualCapacity(m_Edges) > 0 && connection.GetIncomingResidualCapacity(m_Edges) == 0)
						{
							AddInadmissibleLayerCutElement(nodeValidLayerIndex, m_CurrentLayerIndex, connection.Reverse());
						}
					}
					else if (node3.m_Height != upperCutHeight)
					{
						if (connection.GetIncomingResidualCapacity(m_Edges) > 0)
						{
							BumpInadmissibleLayerCutElement(m_CurrentLayerIndex, nodeValidLayerIndex, in connection);
						}
					}
					else if (connection.GetOutgoingResidualCapacity(m_Edges) > 0)
					{
						BumpAdmissibleLayerCutElement(m_CurrentLayerIndex, nodeValidLayerIndex, in connection);
					}
					else if (connection.GetIncomingResidualCapacity(m_Edges) > 0)
					{
						BumpInadmissibleLayerCutElement(m_CurrentLayerIndex, nodeValidLayerIndex, in connection);
					}
				}
				else
				{
					int outgoingResidualCapacity = connection.GetOutgoingResidualCapacity(m_Edges);
					if (outgoingResidualCapacity > 0)
					{
						AugmentOutgoingTempFlow(in connection, outgoingResidualCapacity);
						node3.m_Version = m_CurrentActiveVersion;
						edge.m_CutElementId = node3.m_CutElementId;
						m_ActiveQueue.ElementAt(node3.m_Height - lowerCutHeight).Add(in item);
						result = true;
					}
				}
			}
		}
		return result;
	}
```

- `public LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  

```csharp
public void LoadState(NativeReference<MaxFlowSolverState> solverState, NativeList<LayerState> layerStates, NativeList<CutElement> layerElements, NativeList<CutElementRef> layerElementRefs)
	{
		MaxFlowSolverState value = solverState.Value;
		m_Complete = value.m_Complete;
		m_NextLayerIndex = value.m_NextLayerIndex;
		m_CurrentLabelVersion = value.m_CurrentLabelVersion;
		m_CurrentActiveVersion = value.m_CurrentActiveVersion;
		int elementIndex = 0;
		int elementRefIndex = 0;
		for (int i = 0; i < layerStates.Length; i++)
		{
			m_Layers.Add(Layer.Load(layerStates[i], layerElements.AsArray(), ref elementIndex, layerElementRefs.AsArray(), ref elementRefIndex));
		}
	}
```

- `public ResetNetwork() : System.Void`  

```csharp
public static void ResetNetwork(NativeArray<Node> nodes, NativeArray<Edge> edges, int sourceNode)
	{
		for (int i = 0; i < nodes.Length; i++)
		{
			ref Node reference = ref nodes.ElementAt(i);
			reference.m_Height = 16777216;
			reference.m_Excess = 0;
			reference.m_CutElementId = default(Identifier);
			reference.m_Version = 0;
			reference.m_Retreat = false;
		}
		for (int j = 0; j < edges.Length; j++)
		{
			ref Edge reference2 = ref edges.ElementAt(j);
			reference2.m_CutElementId = default(Identifier);
			reference2.FinalizeTempFlow();
		}
		nodes.ElementAt(sourceNode).m_Height = 0;
	}
```

- `public static ResetNetwork(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes, Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges, System.Int32 sourceNode) : System.Void`  

```csharp
public static void ResetNetwork(NativeArray<Node> nodes, NativeArray<Edge> edges, int sourceNode)
	{
		for (int i = 0; i < nodes.Length; i++)
		{
			ref Node reference = ref nodes.ElementAt(i);
			reference.m_Height = 16777216;
			reference.m_Excess = 0;
			reference.m_CutElementId = default(Identifier);
			reference.m_Version = 0;
			reference.m_Retreat = false;
		}
		for (int j = 0; j < edges.Length; j++)
		{
			ref Edge reference2 = ref edges.ElementAt(j);
			reference2.m_CutElementId = default(Identifier);
			reference2.FinalizeTempFlow();
		}
		nodes.ElementAt(sourceNode).m_Height = 0;
	}
```

- `private RetreatActiveLayer(System.Int32 activeLayerIndex) : System.Void`  

```csharp
private void RetreatActiveLayer(int activeLayerIndex)
	{
		bool flag = activeLayerIndex == m_CurrentLayerIndex;
		for (int i = 0; i < m_LayerHeight; i++)
		{
			bool flag2 = flag && i == 0;
			bool flag3 = i == m_LayerHeight - 1;
			ref UnsafeList<int> reference = ref m_ActiveQueue.ElementAt(i);
			for (int j = 0; j < reference.Length; j++)
			{
				m_StepCounter++;
				int index = reference[j];
				ref Node node = ref GetNode(index);
				Assert.IsFalse(node.m_Excess < 0);
				Assert.IsTrue(node.m_Excess > 0 || node.m_Retreat);
				node.m_Retreat = false;
				int num = node.m_Height + 1;
				GetTotalAdvancedFlow(node, num, out var branchFlow, out var sinkFlow, out var sinkConnection);
				Assert.IsTrue(sinkFlow == 0 || m_CurrentLayerIndex == activeLayerIndex);
				Assert.IsFalse(branchFlow + sinkFlow < node.m_Excess);
				if (flag2)
				{
					Layer layer = GetLayer(activeLayerIndex);
					layer.GetCutElement(node.m_CutElementId.m_Index).isChanged = true;
				}
				for (int k = node.m_FirstConnection; k < node.m_LastConnection; k++)
				{
					Connection connection = GetConnection(k);
					int value = connection.m_EndNode;
					if (value == m_SinkNode)
					{
						continue;
					}
					ref Node node2 = ref GetNode(value);
					if (node2.m_Height != num)
					{
						continue;
					}
					if (branchFlow != 0)
					{
						int outgoingTempFlow = GetOutgoingTempFlow(in connection);
						if (outgoingTempFlow != 0)
						{
							float num2 = (float)outgoingTempFlow / (float)branchFlow;
							branchFlow -= outgoingTempFlow;
							int lowerBound = math.clamp(node.m_Excess - branchFlow, 0, outgoingTempFlow);
							int upperBound = math.min(outgoingTempFlow, node.m_Excess);
							int num3 = math.clamp(Mathf.RoundToInt((float)node.m_Excess * num2), lowerBound, upperBound);
							if (num3 != 0)
							{
								AugmentIncomingTempFlow(in connection, num3);
							}
						}
					}
					if (node2.m_Version != m_CurrentActiveVersion && (node2.m_Excess != 0 || node2.m_Retreat))
					{
						node2.m_Version = m_CurrentActiveVersion;
						int index2 = ((!flag3) ? (i + 1) : 0);
						m_ActiveQueue.ElementAt(index2).Add(in value);
					}
				}
				if (node.m_Excess > 0 && sinkFlow > 0)
				{
					Assert.IsTrue(node.m_Excess <= sinkFlow);
					AugmentIncomingTempFlow(in sinkConnection, node.m_Excess);
				}
				Assert.AreEqual(0, node.m_Excess);
			}
			reference.Clear();
		}
	}
```

- `private RetreatFromLayer(System.Int32 retreatLayerIndex) : System.Void`  

```csharp
private void RetreatFromLayer(int retreatLayerIndex)
	{
		m_CurrentActiveVersion++;
		Layer layer = GetLayer(retreatLayerIndex);
		ref UnsafeList<int> reference = ref m_ActiveQueue.ElementAt(0);
		for (int i = 0; i < layer.m_Elements.Length; i++)
		{
			CutElement cutElement = layer.GetCutElement(i);
			if (cutElement.isAdmissible)
			{
				ref Node node = ref GetNode(cutElement.m_EndNode);
				if ((node.m_Retreat || node.m_Excess > 0) && node.m_Version != m_CurrentActiveVersion)
				{
					node.m_Version = m_CurrentActiveVersion;
					reference.Add(in cutElement.m_EndNode);
				}
			}
		}
		for (int j = retreatLayerIndex; j <= m_CurrentLayerIndex; j++)
		{
			RetreatActiveLayer(j);
		}
	}
```

- `public SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  

```csharp
public void SaveState(NativeReference<MaxFlowSolverState> solverState, NativeList<LayerState> layerStates, NativeList<CutElement> layerElements, NativeList<CutElementRef> layerElementRefs)
	{
		solverState.Value = new MaxFlowSolverState
		{
			m_Complete = m_Complete,
			m_NextLayerIndex = m_NextLayerIndex,
			m_CurrentLabelVersion = m_CurrentLabelVersion,
			m_CurrentActiveVersion = m_CurrentActiveVersion
		};
		layerStates.Length = 0;
		layerElements.Length = 0;
		layerElementRefs.Length = 0;
		if (!m_Complete)
		{
			for (int i = 0; i < m_Layers.Length; i++)
			{
				m_Layers[i].Save(layerStates, layerElements, layerElementRefs);
			}
		}
	}
```

- `public Solve() : System.Void`  

```csharp
public void Solve()
	{
		while (!m_Complete)
		{
			SolveNextLayer();
		}
	}
```

- `public SolveNextLayer() : System.Void`  

```csharp
public void SolveNextLayer()
	{
		Layer layer = GetLayer(m_NextLayerIndex);
		if (layer.isEmpty)
		{
			m_Complete = true;
			return;
		}
		m_CurrentLayerIndex = m_NextLayerIndex;
		m_NextLayerIndex = m_CurrentLayerIndex + 1;
		m_CurrentActiveVersion++;
		if (m_Layers.Length <= m_NextLayerIndex)
		{
			int initialLength = 2 * math.max(layer.usedElementCount, layer.usedElementRefCount);
			m_Layers.Add(new Layer(initialLength, Allocator.Temp));
		}
		if (LabelPreflow())
		{
			int num = AdvanceToSource();
			if (num <= m_CurrentLayerIndex)
			{
				RetreatFromLayer(num);
			}
		}
	}
```


