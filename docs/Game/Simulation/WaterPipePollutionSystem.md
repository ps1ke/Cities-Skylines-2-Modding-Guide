# Game.Simulation.WaterPipePollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipePollutionSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.Simulation.WaterPipePollutionSystem+TypeHandle __TypeHandle;
    private static const System.Int32 kUpdateInterval;

    public WaterPipePollutionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.Simulation.WaterPipePollutionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipePollutionSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 kUpdateInterval`  

```csharp
private static const System.Int32 kUpdateInterval;
```


## Constructors

- `public WaterPipePollutionSystem()`  

```csharp
public WaterPipePollutionSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.WaterPipePollutionSystem+NodePollutionJob`  
- `Game.Simulation.WaterPipePollutionSystem+EdgePollutionJob`  
- `Game.Simulation.WaterPipePollutionSystem+TypeHandle`  

