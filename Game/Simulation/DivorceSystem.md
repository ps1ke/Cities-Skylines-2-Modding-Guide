# Game.Simulation.DivorceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DivorceSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Colossal.Collections.NativeValue<System.Int32> m_DebugDivorce;
    private Colossal.NativeCounter m_DebugDivorceCount;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
    private Unity.Entities.EntityQuery m_CitizenParametersQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.DivorceSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public DivorceSystem();

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

- `private Colossal.Collections.NativeValue<System.Int32> m_DebugDivorce`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_DebugDivorce;
```

- `private Colossal.NativeCounter m_DebugDivorceCount`  

```csharp
private Colossal.NativeCounter m_DebugDivorceCount;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenParametersQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.DivorceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DivorceSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public DivorceSystem()`  

```csharp
public DivorceSystem();
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

- `Game.Simulation.DivorceSystem+CheckDivorceJob`  
- `Game.Simulation.DivorceSystem+SumDivorceJob`  
- `Game.Simulation.DivorceSystem+TypeHandle`  

