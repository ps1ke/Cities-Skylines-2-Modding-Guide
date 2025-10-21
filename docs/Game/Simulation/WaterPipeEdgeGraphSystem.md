# Game.Simulation.WaterPipeEdgeGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeEdgeGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedEdgeQuery;
    private Game.Simulation.WaterPipeEdgeGraphSystem+TypeHandle __TypeHandle;

    public WaterPipeEdgeGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEdgeQuery;
```

- `private Game.Simulation.WaterPipeEdgeGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeEdgeGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeEdgeGraphSystem()`  

```csharp
public WaterPipeEdgeGraphSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.WaterPipeEdgeGraphSystem+CreateEdgeConnectionsJob`  
- `Game.Simulation.WaterPipeEdgeGraphSystem+TypeHandle`  

