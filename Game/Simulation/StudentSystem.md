# Game.Simulation.StudentSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StudentSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_GotoSchoolQuery;
    private Unity.Entities.EntityQuery m_StudentQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Game.Simulation.StudentSystem+TypeHandle __TypeHandle;

    public StudentSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetStudyOffset(Game.Citizens.Citizen citizen);
    public static Unity.Mathematics.float2 GetTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Boolean IsTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population);
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

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_GotoSchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_GotoSchoolQuery;
```

- `private Unity.Entities.EntityQuery m_StudentQuery`  

```csharp
private Unity.Entities.EntityQuery m_StudentQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Game.Simulation.StudentSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StudentSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public StudentSystem()`  

```csharp
public StudentSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetStudyOffset(Game.Citizens.Citizen citizen) : System.Single`  

```csharp
public static System.Single GetStudyOffset(Game.Citizens.Citizen citizen);
```

- `public static GetTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static IsTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population) : System.Boolean`  

```csharp
public static System.Boolean IsTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population);
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

- `Game.Simulation.StudentSystem+GoToSchoolJob`  
- `Game.Simulation.StudentSystem+StudyJob`  
- `Game.Simulation.StudentSystem+TypeHandle`  

