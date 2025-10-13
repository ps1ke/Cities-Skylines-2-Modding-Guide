# Game.Simulation.BirthSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BirthSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Colossal.Collections.NativeValue<System.Int32> m_DebugBirth;
    private Colossal.NativeCounter m_DebugBirthCounter;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
    private Unity.Entities.EntityQuery m_CitizenParametersQuery;
    public System.Int32 m_BirthChance;
    private Game.Simulation.BirthSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public BirthSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
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

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_DebugBirth`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_DebugBirth;
```

- `private Colossal.NativeCounter m_DebugBirthCounter`  

```csharp
private Colossal.NativeCounter m_DebugBirthCounter;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenParametersQuery;
```

- `public System.Int32 m_BirthChance`  

```csharp
public System.Int32 m_BirthChance;
```

- `private Game.Simulation.BirthSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BirthSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public BirthSystem()`  

```csharp
public BirthSystem();
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

- `Game.Simulation.BirthSystem+CheckBirthJob`  
- `Game.Simulation.BirthSystem+SumBirthJob`  
- `Game.Simulation.BirthSystem+TypeHandle`  

