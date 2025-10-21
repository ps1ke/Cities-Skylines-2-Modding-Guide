# Game.Simulation.FindJobSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FindJobSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_JobSeekerQuery;
    private Unity.Entities.EntityQuery m_ResultsQuery;
    private Unity.Entities.EntityQuery m_FreeQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Collections.NativeArray<System.Int32> m_FreeCache;
    private Colossal.Collections.NativeValue<System.Int32> m_StartedWorking;
    private Unity.Jobs.JobHandle m_WriteDeps;
    private Game.Simulation.FindJobSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATE_INTERVAL;

    public FindJobSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_JobSeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_JobSeekerQuery;
```

- `private Unity.Entities.EntityQuery m_ResultsQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResultsQuery;
```

- `private Unity.Entities.EntityQuery m_FreeQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreeQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Collections.NativeArray<System.Int32> m_FreeCache`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_FreeCache;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_StartedWorking`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_StartedWorking;
```

- `private Unity.Jobs.JobHandle m_WriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_WriteDeps;
```

- `private Game.Simulation.FindJobSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FindJobSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATE_INTERVAL`  

```csharp
private static const System.Int32 UPDATE_INTERVAL;
```


## Constructors

- `public FindJobSystem()`  

```csharp
public FindJobSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.FindJobSystem+CalculateFreeWorkplaceJob`  
- `Game.Simulation.FindJobSystem+FindJobJob`  
- `Game.Simulation.FindJobSystem+StartWorkingJob`  
- `Game.Simulation.FindJobSystem+TypeHandle`  

