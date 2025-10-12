# Game.Simulation.ElectricityFlowJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeReference<Game.Simulation.ElectricityFlowJob+State> m_State`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges`  
- `public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections`  
- `public Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices`  
- `public Unity.Collections.NativeArray<System.Int32> m_ChargeNodes`  
- `public Unity.Collections.NativeArray<System.Int32> m_DischargeNodes`  
- `public Unity.Collections.NativeArray<System.Int32> m_TradeNodes`  
- `public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_SolverState`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements`  
- `public Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs`  
- `public Unity.Collections.NativeQueue<System.Int32> m_LabelQueue`  
- `public System.Int32 m_LayerHeight`  
- `public System.Int32 m_FrameCount`  
- `public System.Boolean m_FinalFrame`  
- `private static const System.Int32 kConnectedNodeLabel`  
- `private static const System.Int32 kShortageNodeLabel`  
- `private static const System.Int32 kBeforeBottleneckNodeLabel`  
- `private static const System.Int32 kBeyondBottleneckNodeLabel`  
- `public static const System.Int32 kConnectedEdgeLabel`  
- `public static const System.Int32 kBottleneckEdgeLabel`  
- `public static const System.Int32 kBeyondBottleneckEdgeLabel`  

## Methods

- `private DisableConnections(Unity.Collections.NativeArray<System.Int32> nodes) : System.Void`  
- `private EnableChargeConnectionsIfNoShortage() : System.Void`  
- `private EnableDischargeConnectionsIfShortage() : System.Void`  
- `private EnableTradeConnections() : System.Void`  
- `public Execute() : System.Void`  
- `private ExecutePhase(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 maxSteps) : System.Void`  
- `private Finalize(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  
- `private InitialPhase(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  
- `private LabelBottlenecks(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  
- `private LabelBottleneckSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex) : System.Void`  
- `private LabelConnected(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  
- `private LabelConnectedSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex) : System.Void`  
- `private LabelShortages(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  
- `private LabelShortageSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex) : System.Void`  
- `private MaxFlowPhase(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.ElectricityFlowJob+Phase phaseAfterCompletion) : System.Void`  
- `private PostBatteryPhase(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  
- `private PostProducerPhase(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  
- `private PostTradePhase(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  
- `private ResetSolverState() : System.Void`  
- `private SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export) : System.Void`  

## Nested types

- `Game.Simulation.ElectricityFlowJob+Phase`  
- `Game.Simulation.ElectricityFlowJob+State`  

