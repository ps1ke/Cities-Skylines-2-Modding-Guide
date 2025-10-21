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
private System.Void AddAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection);
```

- `private AddInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  

```csharp
private System.Void AddInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection);
```

- `private AdvanceActiveLayer(System.Int32 activeLayerIndex, System.Int32& retreatLayerIndex) : System.Void`  

```csharp
private System.Void AdvanceActiveLayer(System.Int32 activeLayerIndex, System.Int32& retreatLayerIndex);
```

- `private AdvanceToSource() : System.Int32`  

```csharp
private System.Int32 AdvanceToSource();
```

- `private AugmentIncomingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow) : System.Void`  

```csharp
private System.Void AugmentIncomingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow);
```

- `private AugmentOutgoingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow) : System.Void`  

```csharp
private System.Void AugmentOutgoingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow);
```

- `private BumpAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  

```csharp
private System.Void BumpAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection);
```

- `private BumpInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  

```csharp
private System.Void BumpInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection);
```

- `private CreateElementLink(System.Int32 lowerLayerIndex, System.Int32 lowerElementIndex, System.Int32 higherLayerIndex, System.Int32 higherElementIndex) : System.Void`  

```csharp
private System.Void CreateElementLink(System.Int32 lowerLayerIndex, System.Int32 lowerElementIndex, System.Int32 higherLayerIndex, System.Int32 higherElementIndex);
```

- `private DeleteLinkedElements(System.Int32 lowerLayerIndex, System.Int32 index) : System.Void`  

```csharp
private System.Void DeleteLinkedElements(System.Int32 lowerLayerIndex, System.Int32 index);
```

- `private FinalizeTempFlow(Game.Simulation.Flow.Connection& connection) : System.Void`  

```csharp
private System.Void FinalizeTempFlow(Game.Simulation.Flow.Connection& connection);
```

- `private GetConnection(System.Int32 index) : Game.Simulation.Flow.Connection`  

```csharp
private Game.Simulation.Flow.Connection GetConnection(System.Int32 index);
```

- `private GetEdge(System.Int32 index) : Game.Simulation.Flow.Edge&`  

```csharp
private Game.Simulation.Flow.Edge& GetEdge(System.Int32 index);
```

- `private GetLayer(System.Int32 index) : Game.Simulation.Flow.Layer&`  

```csharp
private Game.Simulation.Flow.Layer& GetLayer(System.Int32 index);
```

- `private GetLayerIndexForHeight(System.Int32 height) : System.Int32`  

```csharp
private System.Int32 GetLayerIndexForHeight(System.Int32 height);
```

- `private GetLowerCutHeight(System.Int32 layerIndex) : System.Int32`  

```csharp
private System.Int32 GetLowerCutHeight(System.Int32 layerIndex);
```

- `private GetNode(System.Int32 index) : Game.Simulation.Flow.Node&`  

```csharp
private Game.Simulation.Flow.Node& GetNode(System.Int32 index);
```

- `private GetNodeValidLayerIndex(Game.Simulation.Flow.Node node) : System.Int32`  

```csharp
private System.Int32 GetNodeValidLayerIndex(Game.Simulation.Flow.Node node);
```

- `private GetOutgoingTempFlow(Game.Simulation.Flow.Connection& connection) : System.Int32`  

```csharp
private System.Int32 GetOutgoingTempFlow(Game.Simulation.Flow.Connection& connection);
```

- `private GetTotalAdvancedFlow(Game.Simulation.Flow.Node currentNode, System.Int32 heightPlusOne, System.Int32& branchFlow, System.Int32& sinkFlow, Game.Simulation.Flow.Connection& sinkConnection) : System.Void`  

```csharp
private System.Void GetTotalAdvancedFlow(Game.Simulation.Flow.Node currentNode, System.Int32 heightPlusOne, System.Int32& branchFlow, System.Int32& sinkFlow, Game.Simulation.Flow.Connection& sinkConnection);
```

- `private GetUpperCutHeight(System.Int32 layerIndex) : System.Int32`  

```csharp
private System.Int32 GetUpperCutHeight(System.Int32 layerIndex);
```

- `public InitializeState() : System.Void`  

```csharp
public System.Void InitializeState();
```

- `private LabelPreflow() : System.Boolean`  

```csharp
private System.Boolean LabelPreflow();
```

- `public LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  

```csharp
public System.Void LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs);
```

- `public ResetNetwork() : System.Void`  

```csharp
public System.Void ResetNetwork();
```

- `public static ResetNetwork(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes, Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges, System.Int32 sourceNode) : System.Void`  

```csharp
public static System.Void ResetNetwork(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes, Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges, System.Int32 sourceNode);
```

- `private RetreatActiveLayer(System.Int32 activeLayerIndex) : System.Void`  

```csharp
private System.Void RetreatActiveLayer(System.Int32 activeLayerIndex);
```

- `private RetreatFromLayer(System.Int32 retreatLayerIndex) : System.Void`  

```csharp
private System.Void RetreatFromLayer(System.Int32 retreatLayerIndex);
```

- `public SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  

```csharp
public System.Void SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs);
```

- `public Solve() : System.Void`  

```csharp
public System.Void Solve();
```

- `public SolveNextLayer() : System.Void`  

```csharp
public System.Void SolveNextLayer();
```


