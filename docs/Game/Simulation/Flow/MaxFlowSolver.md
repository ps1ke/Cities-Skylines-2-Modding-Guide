# Game.Simulation.Flow.MaxFlowSolver

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public System.Int32 m_LayerHeight`  
- `public System.Int32 m_SourceNode`  
- `public System.Int32 m_SinkNode`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.Layer> m_Layers`  
- `public Unity.Collections.NativeQueue<System.Int32> m_LabelQueue`  
- `public Unity.Collections.NativeArray<Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32>> m_ActiveQueue`  
- `public System.Boolean m_Complete`  
- `public System.Int32 m_CurrentLayerIndex`  
- `public System.Int32 m_NextLayerIndex`  
- `public System.Int32 m_CurrentLabelVersion`  
- `public System.Int32 m_CurrentActiveVersion`  
- `public System.Int32 m_StepCounter`  
- `public static const System.Int32 kMaxNodes`  

## Methods

- `private AddAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  
- `private AddInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  
- `private AdvanceActiveLayer(System.Int32 activeLayerIndex, System.Int32& retreatLayerIndex) : System.Void`  
- `private AdvanceToSource() : System.Int32`  
- `private AugmentIncomingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow) : System.Void`  
- `private AugmentOutgoingTempFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow) : System.Void`  
- `private BumpAdmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  
- `private BumpInadmissibleLayerCutElement(System.Int32 lowerLayerIndex, System.Int32 higherLayerIndex, Game.Simulation.Flow.Connection& lhConnection) : System.Void`  
- `private CreateElementLink(System.Int32 lowerLayerIndex, System.Int32 lowerElementIndex, System.Int32 higherLayerIndex, System.Int32 higherElementIndex) : System.Void`  
- `private DeleteLinkedElements(System.Int32 lowerLayerIndex, System.Int32 index) : System.Void`  
- `private FinalizeTempFlow(Game.Simulation.Flow.Connection& connection) : System.Void`  
- `private GetConnection(System.Int32 index) : Game.Simulation.Flow.Connection`  
- `private GetEdge(System.Int32 index) : Game.Simulation.Flow.Edge&`  
- `private GetLayer(System.Int32 index) : Game.Simulation.Flow.Layer&`  
- `private GetLayerIndexForHeight(System.Int32 height) : System.Int32`  
- `private GetLowerCutHeight(System.Int32 layerIndex) : System.Int32`  
- `private GetNode(System.Int32 index) : Game.Simulation.Flow.Node&`  
- `private GetNodeValidLayerIndex(Game.Simulation.Flow.Node node) : System.Int32`  
- `private GetOutgoingTempFlow(Game.Simulation.Flow.Connection& connection) : System.Int32`  
- `private GetTotalAdvancedFlow(Game.Simulation.Flow.Node currentNode, System.Int32 heightPlusOne, System.Int32& branchFlow, System.Int32& sinkFlow, Game.Simulation.Flow.Connection& sinkConnection) : System.Void`  
- `private GetUpperCutHeight(System.Int32 layerIndex) : System.Int32`  
- `public InitializeState() : System.Void`  
- `private LabelPreflow() : System.Boolean`  
- `public LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  
- `public ResetNetwork() : System.Void`  
- `public static ResetNetwork(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes, Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges, System.Int32 sourceNode) : System.Void`  
- `private RetreatActiveLayer(System.Int32 activeLayerIndex) : System.Void`  
- `private RetreatFromLayer(System.Int32 retreatLayerIndex) : System.Void`  
- `public SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> solverState, Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  
- `public Solve() : System.Void`  
- `public SolveNextLayer() : System.Void`  

