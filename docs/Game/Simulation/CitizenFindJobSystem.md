# Game.Simulation.CitizenFindJobSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenFindJobSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_UnemployedQuery;
    private Unity.Entities.EntityQuery m_EmployedQuery;
    private Unity.Entities.EntityQuery m_CitizenParametersQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CitizenFindJobSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kJobSeekCoolDownMax;
    public static readonly System.Int32 kJobSeekCoolDownMin;

    public CitizenFindJobSystem();

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

- `private Unity.Entities.EntityQuery m_UnemployedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnemployedQuery;
```

- `private Unity.Entities.EntityQuery m_EmployedQuery`  

```csharp
private Unity.Entities.EntityQuery m_EmployedQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenParametersQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CitizenFindJobSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CitizenFindJobSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kJobSeekCoolDownMax`  

```csharp
public static readonly System.Int32 kJobSeekCoolDownMax;
```

- `public static readonly System.Int32 kJobSeekCoolDownMin`  

```csharp
public static readonly System.Int32 kJobSeekCoolDownMin;
```


## Constructors

- `public CitizenFindJobSystem()`  

```csharp
public CitizenFindJobSystem();
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

- `Game.Simulation.CitizenFindJobSystem+CitizenFindJobJob`  
- `Game.Simulation.CitizenFindJobSystem+TypeHandle`  

