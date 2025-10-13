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
private System.Void EnableTradeConnections();
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private ExecutePhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps) : System.Void`  

```csharp
private System.Void ExecutePhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps);
```

- `private Finalize(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private System.Void Finalize(Game.Simulation.WaterPipeFlowJob+State& state);
```

- `private FinalizeFlows() : System.Void`  

```csharp
private System.Void FinalizeFlows();
```

- `private FluidFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps) : System.Void`  

```csharp
private System.Void FluidFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps);
```

- `private InitialPhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private System.Void InitialPhase(Game.Simulation.WaterPipeFlowJob+State& state);
```

- `private LabelConnected(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private System.Void LabelConnected(Game.Simulation.WaterPipeFlowJob+State& state);
```

- `private LabelConnectedSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue) : System.Void`  

```csharp
private System.Void LabelConnectedSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue);
```

- `private LabelShortages(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private System.Void LabelShortages(Game.Simulation.WaterPipeFlowJob+State& state);
```

- `private LabelShortageSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue) : System.Void`  

```csharp
private System.Void LabelShortageSubGraph(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 initialNodeIndex, Unity.Collections.NativeQueue<System.Int32> labelQueue);
```

- `private LimitImportEdgeCapacity() : System.Void`  

```csharp
private System.Void LimitImportEdgeCapacity();
```

- `private MaxFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.WaterPipeFlowJob+Phase phaseAfterCompletion) : System.Void`  

```csharp
private System.Void MaxFlowPhase(Game.Simulation.WaterPipeFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.WaterPipeFlowJob+Phase phaseAfterCompletion);
```

- `private PostProducerPhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private System.Void PostProducerPhase(Game.Simulation.WaterPipeFlowJob+State& state);
```

- `private PostTradePhase(Game.Simulation.WaterPipeFlowJob+State& state) : System.Void`  

```csharp
private System.Void PostTradePhase(Game.Simulation.WaterPipeFlowJob+State& state);
```

- `private PreflowSinkEdges() : System.Void`  

```csharp
private System.Void PreflowSinkEdges();
```

- `private ResetMaxFlowState() : System.Void`  

```csharp
private System.Void ResetMaxFlowState();
```

- `private ResetNonSinkEdges() : System.Void`  

```csharp
private System.Void ResetNonSinkEdges();
```

- `private SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export) : System.Void`  

```csharp
private System.Void SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export);
```


## Nested types

- `Game.Simulation.WaterPipeFlowJob+Phase`  
- `Game.Simulation.WaterPipeFlowJob+State`  
- `Game.Simulation.WaterPipeFlowJob+Data`  

