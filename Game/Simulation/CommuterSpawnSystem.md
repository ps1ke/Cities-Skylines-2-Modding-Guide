# Game.Simulation.CommuterSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CommuterSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_CommuterQuery;
    private Unity.Entities.EntityQuery m_WorkerQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.CommuterSpawnSystem+TypeHandle __TypeHandle;

    public CommuterSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_CommuterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommuterQuery;
```

- `private Unity.Entities.EntityQuery m_WorkerQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkerQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.CommuterSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CommuterSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CommuterSpawnSystem()`  

```csharp
public CommuterSpawnSystem();
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

- `Game.Simulation.CommuterSpawnSystem+SpawnCommuterHouseholdJob`  
- `Game.Simulation.CommuterSpawnSystem+TypeHandle`  

