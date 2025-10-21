# Game.Simulation.CriminalSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CriminalSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_CriminalQuery;
    private Unity.Entities.EntityQuery m_PoliceConfigQuery;
    private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CriminalSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 SYSTEM_UPDATE_INTERVAL;

    public CriminalSystem();

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

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_CriminalQuery`  

```csharp
private Unity.Entities.EntityQuery m_CriminalQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CriminalSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CriminalSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 SYSTEM_UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 SYSTEM_UPDATE_INTERVAL;
```


## Constructors

- `public CriminalSystem()`  

```csharp
public CriminalSystem();
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

- `Game.Simulation.CriminalSystem+CrimeData`  
- `Game.Simulation.CriminalSystem+CriminalJob`  
- `Game.Simulation.CriminalSystem+CrimeJob`  
- `Game.Simulation.CriminalSystem+TypeHandle`  

