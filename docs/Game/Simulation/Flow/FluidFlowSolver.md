# Game.Simulation.Flow.FluidFlowSolver

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public System.Int32 m_SourceNode`  
- `public System.Int32 m_SinkNode`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections`  
- `public Colossal.Collections.NativeMinHeap<Game.Simulation.Flow.LabelHeapData> m_LabelQueue`  
- `public Colossal.Collections.NativeMinHeap<Game.Simulation.Flow.PushHeapData> m_PushQueue`  
- `public System.Boolean m_Complete`  
- `public System.Int32 m_CurrentVersion`  
- `public System.Int32 m_StepCounter`  

## Methods

- `private AugmentOutgoingFinalFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow) : System.Void`  
- `private GetConnection(System.Int32 index) : Game.Simulation.Flow.Connection`  
- `private GetEdge(System.Int32 index) : Game.Simulation.Flow.Edge&`  
- `private GetLength(Game.Simulation.Flow.Connection connection) : System.Int32`  
- `private GetMaxAdditionalOutgoingFlow(Game.Simulation.Flow.Connection connection) : System.Int32`  
- `private GetNode(System.Int32 index) : Game.Simulation.Flow.Node&`  
- `public InitializeState() : System.Void`  
- `private Label() : System.Void`  
- `public LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState) : System.Void`  
- `public Preflow() : System.Void`  
- `private Push() : System.Void`  
- `public ResetFlows() : System.Void`  
- `public static ResetFlows(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Void`  
- `public ResetNodes() : System.Void`  
- `public static ResetNodes(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes) : System.Void`  
- `public SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState) : System.Void`  
- `public Solve() : System.Void`  
- `public SolveStep() : System.Void`  

