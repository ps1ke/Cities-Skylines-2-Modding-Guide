# Game.Simulation.LookForPartnerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LookForPartnerSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_LookingQuery;
    private Unity.Entities.EntityQuery m_CitizenParametersQuery;
    private Unity.Collections.NativeQueue<Game.Citizens.LookingForPartner> m_Queue;
    private Colossal.Collections.NativeValue<System.Int32> m_DebugLookingForPartner;
    private Game.Simulation.LookForPartnerSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public LookForPartnerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_LookingQuery`  

```csharp
private Unity.Entities.EntityQuery m_LookingQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenParametersQuery;
```

- `private Unity.Collections.NativeQueue<Game.Citizens.LookingForPartner> m_Queue`  

```csharp
private Unity.Collections.NativeQueue<Game.Citizens.LookingForPartner> m_Queue;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_DebugLookingForPartner`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_DebugLookingForPartner;
```

- `private Game.Simulation.LookForPartnerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LookForPartnerSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public LookForPartnerSystem()`  

```csharp
public LookForPartnerSystem();
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

- `Game.Simulation.LookForPartnerSystem+AddPartnerSeekerJob`  
- `Game.Simulation.LookForPartnerSystem+LookForPartnerJob`  
- `Game.Simulation.LookForPartnerSystem+TypeHandle`  

