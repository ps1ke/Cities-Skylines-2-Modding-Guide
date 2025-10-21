# Game.Simulation.TrafficFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficFlowSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_RoadQuery;
    private Game.Simulation.TrafficFlowSystem+TypeHandle __TypeHandle;
    public static const System.Int32 UPDATES_PER_DAY;

    public TrafficFlowSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_RoadQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadQuery;
```

- `private Game.Simulation.TrafficFlowSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrafficFlowSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 UPDATES_PER_DAY`  

```csharp
public static const System.Int32 UPDATES_PER_DAY;
```


## Constructors

- `public TrafficFlowSystem()`  

```csharp
public TrafficFlowSystem();
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

- `Game.Simulation.TrafficFlowSystem+UpdateLaneFlowJob`  
- `Game.Simulation.TrafficFlowSystem+UpdateRoadFlowJob`  
- `Game.Simulation.TrafficFlowSystem+TypeHandle`  

