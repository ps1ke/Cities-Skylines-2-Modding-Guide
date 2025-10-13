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
private System.Void AugmentOutgoingFinalFlow(Game.Simulation.Flow.Connection& connection, System.Int32 flow);
```

- `private GetConnection(System.Int32 index) : Game.Simulation.Flow.Connection`  

```csharp
private Game.Simulation.Flow.Connection GetConnection(System.Int32 index);
```

- `private GetEdge(System.Int32 index) : Game.Simulation.Flow.Edge&`  

```csharp
private Game.Simulation.Flow.Edge& GetEdge(System.Int32 index);
```

- `private GetLength(Game.Simulation.Flow.Connection connection) : System.Int32`  

```csharp
private System.Int32 GetLength(Game.Simulation.Flow.Connection connection);
```

- `private GetMaxAdditionalOutgoingFlow(Game.Simulation.Flow.Connection connection) : System.Int32`  

```csharp
private System.Int32 GetMaxAdditionalOutgoingFlow(Game.Simulation.Flow.Connection connection);
```

- `private GetNode(System.Int32 index) : Game.Simulation.Flow.Node&`  

```csharp
private Game.Simulation.Flow.Node& GetNode(System.Int32 index);
```

- `public InitializeState() : System.Void`  

```csharp
public System.Void InitializeState();
```

- `private Label() : System.Void`  

```csharp
private System.Void Label();
```

- `public LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState) : System.Void`  

```csharp
public System.Void LoadState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState);
```

- `public Preflow() : System.Void`  

```csharp
public System.Void Preflow();
```

- `private Push() : System.Void`  

```csharp
private System.Void Push();
```

- `public ResetFlows() : System.Void`  

```csharp
public System.Void ResetFlows();
```

- `public static ResetFlows(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Void`  

```csharp
public static System.Void ResetFlows(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges);
```

- `public ResetNodes() : System.Void`  

```csharp
public System.Void ResetNodes();
```

- `public static ResetNodes(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes) : System.Void`  

```csharp
public static System.Void ResetNodes(Unity.Collections.NativeArray<Game.Simulation.Flow.Node> nodes);
```

- `public SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState) : System.Void`  

```csharp
public System.Void SaveState(Unity.Collections.NativeReference<Game.Simulation.Flow.FluidFlowSolverState> solverState);
```

- `public Solve() : System.Void`  

```csharp
public System.Void Solve();
```

- `public SolveStep() : System.Void`  

```csharp
public System.Void SolveStep();
```


