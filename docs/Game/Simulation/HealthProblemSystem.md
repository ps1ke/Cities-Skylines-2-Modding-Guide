# Game.Simulation.HealthProblemSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HealthProblemSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.EntityQuery m_HealthProblemQuery;
    private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
    private Unity.Entities.EntityQuery m_FireSettingsQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.HealthProblemSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 SYSTEM_UPDATE_INTERVAL;

    public HealthProblemSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.EntityQuery m_HealthProblemQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthProblemQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_FireSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireSettingsQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.HealthProblemSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HealthProblemSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 SYSTEM_UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 SYSTEM_UPDATE_INTERVAL;
```


## Constructors

- `public HealthProblemSystem()`  

```csharp
public HealthProblemSystem();
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

- `Game.Simulation.HealthProblemSystem+HealthProblemJob`  
- `Game.Simulation.HealthProblemSystem+TypeHandle`  

