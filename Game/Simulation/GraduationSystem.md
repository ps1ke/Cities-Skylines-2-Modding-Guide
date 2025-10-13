# Game.Simulation.GraduationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GraduationSystem : Game.GameSystemBase
{
    public System.Int32 debugFastGraduationLevel;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityQuery m_StudentQuery;
    private Game.Simulation.GraduationSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1855827631_0;
    private Unity.Entities.EntityQuery __query_1855827631_1;
    public static const System.Int32 kUpdatesPerDay;
    public static const System.Int32 kCheckSlowdown;

    public GraduationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetDropoutProbability(Game.Citizens.Citizen citizen, System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData& economyParameters, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single efficiency, Game.Common.TimeData timeData);
    public static System.Single GetDropoutProbability(System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.Single age, System.Single studyWillingness, System.Int32 failedEducationCount, System.Single graduationProbability, Game.Prefabs.EconomyParameterData& economyParameters);
    public static System.Single GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single studyWillingness, System.Single efficiency);
    public static System.Single GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, System.Single graduationModifier, Unity.Mathematics.float2 collegeModifier, Unity.Mathematics.float2 uniModifier, System.Single studyWillingness, System.Single efficiency);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public System.Int32 debugFastGraduationLevel`  

```csharp
public System.Int32 debugFastGraduationLevel;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityQuery m_StudentQuery`  

```csharp
private Unity.Entities.EntityQuery m_StudentQuery;
```

- `private Game.Simulation.GraduationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.GraduationSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1855827631_0`  

```csharp
private Unity.Entities.EntityQuery __query_1855827631_0;
```

- `private Unity.Entities.EntityQuery __query_1855827631_1`  

```csharp
private Unity.Entities.EntityQuery __query_1855827631_1;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```

- `public static const System.Int32 kCheckSlowdown`  

```csharp
public static const System.Int32 kCheckSlowdown;
```


## Constructors

- `public GraduationSystem()`  

```csharp
public GraduationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetDropoutProbability(Game.Citizens.Citizen citizen, System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData& economyParameters, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single efficiency, Game.Common.TimeData timeData) : System.Single`  

```csharp
public static System.Single GetDropoutProbability(Game.Citizens.Citizen citizen, System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData& economyParameters, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single efficiency, Game.Common.TimeData timeData);
```

- `public static GetDropoutProbability(System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.Single age, System.Single studyWillingness, System.Int32 failedEducationCount, System.Single graduationProbability, Game.Prefabs.EconomyParameterData& economyParameters) : System.Single`  

```csharp
public static System.Single GetDropoutProbability(System.Int32 level, System.Single commute, System.Single fee, System.Int32 wealth, System.Single age, System.Single studyWillingness, System.Int32 failedEducationCount, System.Single graduationProbability, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public static GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single studyWillingness, System.Single efficiency) : System.Single`  

```csharp
public static System.Single GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, Game.Prefabs.SchoolData schoolData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, System.Single studyWillingness, System.Single efficiency);
```

- `public static GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, System.Single graduationModifier, Unity.Mathematics.float2 collegeModifier, Unity.Mathematics.float2 uniModifier, System.Single studyWillingness, System.Single efficiency) : System.Single`  

```csharp
public static System.Single GetGraduationProbability(System.Int32 level, System.Int32 wellbeing, System.Single graduationModifier, Unity.Mathematics.float2 collegeModifier, Unity.Mathematics.float2 uniModifier, System.Single studyWillingness, System.Single efficiency);
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

- `Game.Simulation.GraduationSystem+GraduationJob`  
- `Game.Simulation.GraduationSystem+TypeHandle`  

