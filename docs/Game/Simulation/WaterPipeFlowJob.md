# Game.Simulation.WaterPipeFlowJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeReference<Game.Simulation.WaterPipeFlowJob+State> m_State`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections`  
- `public Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices`  
- `public Unity.Collections.NativeArray<System.Int32> m_TradeNodes`  
- `public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_MaxFlowState`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs`  
- `public Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> m_FluidFlowState`  
- `public System.Int32 m_ImportCapacity`  
- `public System.Int32 m_ExportCapacity`  
- `public System.Boolean m_FluidFlowEnabled`  
- `public System.Int32 m_LayerHeight`  
- `public System.Int32 m_FrameCount`  
- `public System.Boolean m_FinalFrame`  
- `private static const System.Int32 kShortageNodeLabel`  
- `private static const System.Int32 kConnectedNodeLabel`  
- `public static const System.Int32 kShortageEdgeLabel`  
- `public static const System.Int32 kConnectedEdgeLabel`  
- `private static const System.Int32 kSinkEdgeLabel`  

## Methods

- `private EnableTradeConnections() : System.Void`  
- `public Execute() : System.Void`  
- `private ExecutePhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps) : System.Void`  
- `private Finalize(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  
- `private FinalizeFlows() : System.Void`  
- `private FluidFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps) : System.Void`  
- `private InitialPhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  
- `private LabelConnected(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  
- `private LabelConnectedSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue) : System.Void`  
- `private LabelShortages(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  
- `private LabelShortageSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue) : System.Void`  
- `private LimitImportEdgeCapacity() : System.Void`  
- `private MaxFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.WaterPipeFlowJob+Phase phaseAfterCompletion) : System.Void`  
- `private PostProducerPhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  
- `private PostTradePhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  
- `private PreflowSinkEdges() : System.Void`  
- `private ResetMaxFlowState() : System.Void`  
- `private ResetNonSinkEdges() : System.Void`  
- `private SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export) : System.Void`  

## Nested types

- `Game.Simulation.WaterPipeFlowJob+Phase`  
- `Game.Simulation.WaterPipeFlowJob+State`  
- `Game.Simulation.WaterPipeFlowJob+Data`  

