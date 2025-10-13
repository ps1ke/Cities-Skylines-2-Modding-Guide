# Game.Debug.WaterPipeDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeDebugSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NodeGroup;
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityQuery m_OtherGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.WaterPipeDebugSystem+TypeHandle __TypeHandle;

    public WaterPipeDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Boolean FindEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.Entity& edge, Unity.Entities.DynamicBuffer<Game.Simulation.ConnectedFlowEdge> edgeBuffer, Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> edges);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_NodeGroup;
```

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Unity.Entities.EntityQuery m_OtherGroup`  

```csharp
private Unity.Entities.EntityQuery m_OtherGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.WaterPipeDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.WaterPipeDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeDebugSystem()`  

```csharp
public WaterPipeDebugSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static FindEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.Entity& edge, Unity.Entities.DynamicBuffer<Game.Simulation.ConnectedFlowEdge> edgeBuffer, Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> edges) : System.Boolean`  

```csharp
private static System.Boolean FindEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.Entity& edge, Unity.Entities.DynamicBuffer<Game.Simulation.ConnectedFlowEdge> edgeBuffer, Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> edges);
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

- `Game.Debug.WaterPipeDebugSystem+TypeHandle`  

