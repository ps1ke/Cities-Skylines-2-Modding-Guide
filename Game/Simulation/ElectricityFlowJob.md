# Game.Simulation.ElectricityFlowJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ElectricityFlowJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeReference<Game.Simulation.ElectricityFlowJob+State> m_State;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Node> m_Nodes;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> m_Edges;
    public Unity.Collections.NativeArray<Game.Simulation.Flow.Connection> m_Connections;
    public Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
    public Unity.Collections.NativeArray<System.Int32> m_ChargeNodes;
    public Unity.Collections.NativeArray<System.Int32> m_DischargeNodes;
    public Unity.Collections.NativeArray<System.Int32> m_TradeNodes;
    public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_SolverState;
    public Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates;
    public Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements;
    public Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs;
    public Unity.Collections.NativeQueue<System.Int32> m_LabelQueue;
    public System.Int32 m_LayerHeight;
    public System.Int32 m_FrameCount;
    public System.Boolean m_FinalFrame;
    private static const System.Int32 kConnectedNodeLabel;
    private static const System.Int32 kShortageNodeLabel;
    private static const System.Int32 kBeforeBottleneckNodeLabel;
    private static const System.Int32 kBeyondBottleneckNodeLabel;
    public static const System.Int32 kConnectedEdgeLabel;
    public static const System.Int32 kBottleneckEdgeLabel;
    public static const System.Int32 kBeyondBottleneckEdgeLabel;

    private System.Void DisableConnections(Unity.Collections.NativeArray<System.Int32> nodes);
    private System.Void EnableChargeConnectionsIfNoShortage();
    private System.Void EnableDischargeConnectionsIfShortage();
    private System.Void EnableTradeConnections();
    public System.Void Execute();
    private System.Void ExecutePhase(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 maxSteps);
    private System.Void Finalize(Game.Simulation.ElectricityFlowJob+State& state);
    private System.Void InitialPhase(Game.Simulation.ElectricityFlowJob+State& state);
    private System.Void LabelBottlenecks(Game.Simulation.ElectricityFlowJob+State& state);
    private System.Void LabelBottleneckSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex);
    private System.Void LabelConnected(Game.Simulation.ElectricityFlowJob+State& state);
    private System.Void LabelConnectedSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex);
    private System.Void LabelShortages(Game.Simulation.ElectricityFlowJob+State& state);
    private System.Void LabelShortageSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex);
    private System.Void MaxFlowPhase(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.ElectricityFlowJob+Phase phaseAfterCompletion);
    private System.Void PostBatteryPhase(Game.Simulation.ElectricityFlowJob+State& state);
    private System.Void PostProducerPhase(Game.Simulation.ElectricityFlowJob+State& state);
    private System.Void PostTradePhase(Game.Simulation.ElectricityFlowJob+State& state);
    private System.Void ResetSolverState();
    private System.Void SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export);
}
```


## Fields

- `public Unity.Collections.NativeReference<Game.Simulation.ElectricityFlowJob+State> m_State`  

```csharp
public Unity.Collections.NativeReference<Game.Simulation.ElectricityFlowJob+State> m_State;
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

- `public Unity.Collections.NativeArray<System.Int32> m_ChargeNodes`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_ChargeNodes;
```

- `public Unity.Collections.NativeArray<System.Int32> m_DischargeNodes`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_DischargeNodes;
```

- `public Unity.Collections.NativeArray<System.Int32> m_TradeNodes`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_TradeNodes;
```

- `public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_SolverState`  

```csharp
public Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_SolverState;
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

- `public Unity.Collections.NativeQueue<System.Int32> m_LabelQueue`  

```csharp
public Unity.Collections.NativeQueue<System.Int32> m_LabelQueue;
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

- `private static const System.Int32 kConnectedNodeLabel`  

```csharp
private static const System.Int32 kConnectedNodeLabel;
```

- `private static const System.Int32 kShortageNodeLabel`  

```csharp
private static const System.Int32 kShortageNodeLabel;
```

- `private static const System.Int32 kBeforeBottleneckNodeLabel`  

```csharp
private static const System.Int32 kBeforeBottleneckNodeLabel;
```

- `private static const System.Int32 kBeyondBottleneckNodeLabel`  

```csharp
private static const System.Int32 kBeyondBottleneckNodeLabel;
```

- `public static const System.Int32 kConnectedEdgeLabel`  

```csharp
public static const System.Int32 kConnectedEdgeLabel;
```

- `public static const System.Int32 kBottleneckEdgeLabel`  

```csharp
public static const System.Int32 kBottleneckEdgeLabel;
```

- `public static const System.Int32 kBeyondBottleneckEdgeLabel`  

```csharp
public static const System.Int32 kBeyondBottleneckEdgeLabel;
```


## Methods

- `private DisableConnections(Unity.Collections.NativeArray<System.Int32> nodes) : System.Void`  

```csharp
private System.Void DisableConnections(Unity.Collections.NativeArray<System.Int32> nodes);
```

- `private EnableChargeConnectionsIfNoShortage() : System.Void`  

```csharp
private System.Void EnableChargeConnectionsIfNoShortage();
```

- `private EnableDischargeConnectionsIfShortage() : System.Void`  

```csharp
private System.Void EnableDischargeConnectionsIfShortage();
```

- `private EnableTradeConnections() : System.Void`  

```csharp
private System.Void EnableTradeConnections();
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private ExecutePhase(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 maxSteps) : System.Void`  

```csharp
private System.Void ExecutePhase(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 maxSteps);
```

- `private Finalize(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  

```csharp
private System.Void Finalize(Game.Simulation.ElectricityFlowJob+State& state);
```

- `private InitialPhase(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  

```csharp
private System.Void InitialPhase(Game.Simulation.ElectricityFlowJob+State& state);
```

- `private LabelBottlenecks(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  

```csharp
private System.Void LabelBottlenecks(Game.Simulation.ElectricityFlowJob+State& state);
```

- `private LabelBottleneckSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex) : System.Void`  

```csharp
private System.Void LabelBottleneckSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex);
```

- `private LabelConnected(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  

```csharp
private System.Void LabelConnected(Game.Simulation.ElectricityFlowJob+State& state);
```

- `private LabelConnectedSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex) : System.Void`  

```csharp
private System.Void LabelConnectedSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex);
```

- `private LabelShortages(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  

```csharp
private System.Void LabelShortages(Game.Simulation.ElectricityFlowJob+State& state);
```

- `private LabelShortageSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex) : System.Void`  

```csharp
private System.Void LabelShortageSubGraph(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 initialNodeIndex);
```

- `private MaxFlowPhase(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.ElectricityFlowJob+Phase phaseAfterCompletion) : System.Void`  

```csharp
private System.Void MaxFlowPhase(Game.Simulation.ElectricityFlowJob+State& state, System.Int32 maxSteps, Game.Simulation.ElectricityFlowJob+Phase phaseAfterCompletion);
```

- `private PostBatteryPhase(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  

```csharp
private System.Void PostBatteryPhase(Game.Simulation.ElectricityFlowJob+State& state);
```

- `private PostProducerPhase(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  

```csharp
private System.Void PostProducerPhase(Game.Simulation.ElectricityFlowJob+State& state);
```

- `private PostTradePhase(Game.Simulation.ElectricityFlowJob+State& state) : System.Void`  

```csharp
private System.Void PostTradePhase(Game.Simulation.ElectricityFlowJob+State& state);
```

- `private ResetSolverState() : System.Void`  

```csharp
private System.Void ResetSolverState();
```

- `private SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export) : System.Void`  

```csharp
private System.Void SetTradeConnectionsEnabled(System.Boolean import, System.Boolean export);
```


## Nested types

- `Game.Simulation.ElectricityFlowJob+Phase`  
- `Game.Simulation.ElectricityFlowJob+State`  

