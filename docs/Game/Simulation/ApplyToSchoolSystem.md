# Game.Simulation.ApplyToSchoolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyToSchoolSystem : Game.GameSystemBase
{
    public System.Boolean debugFastApplySchool;
    private Unity.Entities.EntityQuery m_CitizenGroup;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ApplyToSchoolSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2069025490_0;
    private Unity.Entities.EntityQuery __query_2069025490_1;
    private Unity.Entities.EntityQuery __query_2069025490_2;
    public static readonly System.Int32 kCoolDown;
    public static const System.UInt32 UPDATE_INTERVAL;

    public ApplyToSchoolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetEnteringProbability(Game.Citizens.CitizenAge age, System.Boolean worker, System.Int32 level, System.Int32 wellbeing, System.Single willingness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.EducationParameterData& educationParameterData);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public System.Boolean debugFastApplySchool`  

```csharp
public System.Boolean debugFastApplySchool;
```

- `private Unity.Entities.EntityQuery m_CitizenGroup`  

```csharp
private Unity.Entities.EntityQuery m_CitizenGroup;
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

- `private Game.Simulation.ApplyToSchoolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ApplyToSchoolSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2069025490_0`  

```csharp
private Unity.Entities.EntityQuery __query_2069025490_0;
```

- `private Unity.Entities.EntityQuery __query_2069025490_1`  

```csharp
private Unity.Entities.EntityQuery __query_2069025490_1;
```

- `private Unity.Entities.EntityQuery __query_2069025490_2`  

```csharp
private Unity.Entities.EntityQuery __query_2069025490_2;
```

- `public static readonly System.Int32 kCoolDown`  

```csharp
public static readonly System.Int32 kCoolDown;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public ApplyToSchoolSystem()`  

```csharp
public ApplyToSchoolSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetEnteringProbability(Game.Citizens.CitizenAge age, System.Boolean worker, System.Int32 level, System.Int32 wellbeing, System.Single willingness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.EducationParameterData& educationParameterData) : System.Single`  

```csharp
public static System.Single GetEnteringProbability(Game.Citizens.CitizenAge age, System.Boolean worker, System.Int32 level, System.Int32 wellbeing, System.Single willingness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.EducationParameterData& educationParameterData);
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

- `Game.Simulation.ApplyToSchoolSystem+ApplyToSchoolJob`  
- `Game.Simulation.ApplyToSchoolSystem+TypeHandle`  

