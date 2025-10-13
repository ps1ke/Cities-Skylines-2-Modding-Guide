# Game.Simulation.CrimeAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CrimeAccumulationSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_CrimeProducerQuery;
    private Unity.Entities.EntityQuery m_PoliceConfigurationQuery;
    private Unity.Entities.EntityArchetype m_PatrolRequestArchetype;
    private Game.Simulation.CrimeAccumulationSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kUpdateInterval;

    public CrimeAccumulationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceConfigurationQuery;
```

- `private Unity.Entities.EntityArchetype m_PatrolRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PatrolRequestArchetype;
```

- `private Game.Simulation.CrimeAccumulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CrimeAccumulationSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```


## Constructors

- `public CrimeAccumulationSystem()`  

```csharp
public CrimeAccumulationSystem();
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

- `Game.Simulation.CrimeAccumulationSystem+CrimeAccumulationJob`  
- `Game.Simulation.CrimeAccumulationSystem+TypeHandle`  

