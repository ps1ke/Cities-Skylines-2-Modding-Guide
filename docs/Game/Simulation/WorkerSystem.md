# Game.Simulation.WorkerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WorkerSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_GotoWorkQuery;
    private Unity.Entities.EntityQuery m_WorkerQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.WorkerSystem+TypeHandle __TypeHandle;

    public WorkerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Mathematics.float2 GetTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Boolean includeCommute);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Single GetWorkOffset(Game.Citizens.Citizen citizen);
    public static System.Boolean IsTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay);
    public static System.Boolean IsTodayOffDay(Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem`  

```csharp
private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_GotoWorkQuery`  

```csharp
private Unity.Entities.EntityQuery m_GotoWorkQuery;
```

- `private Unity.Entities.EntityQuery m_WorkerQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkerQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.WorkerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WorkerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WorkerSystem()`  

```csharp
public WorkerSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Boolean includeCommute) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Boolean includeCommute);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static GetWorkOffset(Game.Citizens.Citizen citizen) : System.Single`  

```csharp
public static System.Single GetWorkOffset(Game.Citizens.Citizen citizen);
```

- `public static IsTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay) : System.Boolean`  

```csharp
public static System.Boolean IsTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay);
```

- `public static IsTodayOffDay(Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population) : System.Boolean`  

```csharp
public static System.Boolean IsTodayOffDay(Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population);
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

- `Game.Simulation.WorkerSystem+GoToWorkJob`  
- `Game.Simulation.WorkerSystem+WorkJob`  
- `Game.Simulation.WorkerSystem+TypeHandle`  

