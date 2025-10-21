# Game.Simulation.FindSchoolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FindSchoolSystem : Game.GameSystemBase
{
    public System.Boolean debugFastFindSchool;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_SchoolSeekerQuery;
    private Unity.Entities.EntityQuery m_ResultsQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.FindSchoolSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_17488131_0;
    private Unity.Entities.EntityQuery __query_17488131_1;

    public FindSchoolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public System.Boolean debugFastFindSchool`  

```csharp
public System.Boolean debugFastFindSchool;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_SchoolSeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_SchoolSeekerQuery;
```

- `private Unity.Entities.EntityQuery m_ResultsQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResultsQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.FindSchoolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FindSchoolSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_17488131_0`  

```csharp
private Unity.Entities.EntityQuery __query_17488131_0;
```

- `private Unity.Entities.EntityQuery __query_17488131_1`  

```csharp
private Unity.Entities.EntityQuery __query_17488131_1;
```


## Constructors

- `public FindSchoolSystem()`  

```csharp
public FindSchoolSystem();
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

- `Game.Simulation.FindSchoolSystem+FindSchoolJob`  
- `Game.Simulation.FindSchoolSystem+StartStudyingJob`  
- `Game.Simulation.FindSchoolSystem+TypeHandle`  

