# Game.Simulation.ElectricityEdgeGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityEdgeGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedEdgeQuery;
    private Game.Simulation.ElectricityEdgeGraphSystem+TypeHandle __TypeHandle;

    public ElectricityEdgeGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEdgeQuery;
```

- `private Game.Simulation.ElectricityEdgeGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityEdgeGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElectricityEdgeGraphSystem()`  

```csharp
public ElectricityEdgeGraphSystem();
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

- `Game.Simulation.ElectricityEdgeGraphSystem+CreateEdgeConnectionsJob`  
- `Game.Simulation.ElectricityEdgeGraphSystem+TypeHandle`  

