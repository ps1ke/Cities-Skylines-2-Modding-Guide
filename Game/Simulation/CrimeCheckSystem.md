# Game.Simulation.CrimeCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CrimeCheckSystem : Game.GameSystemBase
{
    public readonly System.Int32 kUpdatesPerDay;
    public System.Boolean debugFullCrimeMode;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_PoliceConfigurationQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CrimeCheckSystem+TypeHandle __TypeHandle;

    public CrimeCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public readonly System.Int32 kUpdatesPerDay`  

```csharp
public readonly System.Int32 kUpdatesPerDay;
```

- `public System.Boolean debugFullCrimeMode`  

```csharp
public System.Boolean debugFullCrimeMode;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceConfigurationQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CrimeCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CrimeCheckSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CrimeCheckSystem()`  

```csharp
public CrimeCheckSystem();
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

- `Game.Simulation.CrimeCheckSystem+CrimeCheckJob`  
- `Game.Simulation.CrimeCheckSystem+TypeHandle`  

