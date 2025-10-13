# Game.Simulation.WaterPipeOutsideConnectionGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeOutsideConnectionGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Common.ModificationBarrier3 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedConnectionQuery;
    private Game.Simulation.WaterPipeOutsideConnectionGraphSystem+TypeHandle __TypeHandle;

    public WaterPipeOutsideConnectionGraphSystem();

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

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier3 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedConnectionQuery;
```

- `private Game.Simulation.WaterPipeOutsideConnectionGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeOutsideConnectionGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeOutsideConnectionGraphSystem()`  

```csharp
public WaterPipeOutsideConnectionGraphSystem();
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

- `Game.Simulation.WaterPipeOutsideConnectionGraphSystem+CreateOutsideConnectionsJob`  
- `Game.Simulation.WaterPipeOutsideConnectionGraphSystem+TypeHandle`  

