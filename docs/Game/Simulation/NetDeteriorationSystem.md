# Game.Simulation.NetDeteriorationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetDeteriorationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
    private Game.Simulation.NetDeteriorationSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public NetDeteriorationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetMaintenancePriority(Game.Net.NetCondition condition);
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

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
```

- `private Game.Simulation.NetDeteriorationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.NetDeteriorationSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public NetDeteriorationSystem()`  

```csharp
public NetDeteriorationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetMaintenancePriority(Game.Net.NetCondition condition) : System.Int32`  

```csharp
public static System.Int32 GetMaintenancePriority(Game.Net.NetCondition condition);
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

- `Game.Simulation.NetDeteriorationSystem+UpdateLaneConditionJob`  
- `Game.Simulation.NetDeteriorationSystem+UpdateNetConditionJob`  
- `Game.Simulation.NetDeteriorationSystem+TypeHandle`  

