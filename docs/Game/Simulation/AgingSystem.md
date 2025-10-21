# Game.Simulation.AgingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AgingSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    public Colossal.Collections.NativeValue<System.Int32> m_BecomeTeen;
    public Colossal.Collections.NativeValue<System.Int32> m_BecomeAdult;
    public Colossal.Collections.NativeValue<System.Int32> m_BecomeElder;
    public Colossal.NativeCounter m_BecomeTeenCounter;
    public Colossal.NativeCounter m_BecomeAdultCounter;
    public Colossal.NativeCounter m_BecomeElderCounter;
    private Game.Simulation.AgingSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static System.Boolean s_DebugAgeAllCitizens;

    public AgingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetAdultAgeLimitInDays();
    public static System.Int32 GetElderAgeLimitInDays();
    public static System.Int32 GetTeenAgeLimitInDays();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeTeen`  

```csharp
public Colossal.Collections.NativeValue<System.Int32> m_BecomeTeen;
```

- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeAdult`  

```csharp
public Colossal.Collections.NativeValue<System.Int32> m_BecomeAdult;
```

- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeElder`  

```csharp
public Colossal.Collections.NativeValue<System.Int32> m_BecomeElder;
```

- `public Colossal.NativeCounter m_BecomeTeenCounter`  

```csharp
public Colossal.NativeCounter m_BecomeTeenCounter;
```

- `public Colossal.NativeCounter m_BecomeAdultCounter`  

```csharp
public Colossal.NativeCounter m_BecomeAdultCounter;
```

- `public Colossal.NativeCounter m_BecomeElderCounter`  

```csharp
public Colossal.NativeCounter m_BecomeElderCounter;
```

- `private Game.Simulation.AgingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AgingSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static System.Boolean s_DebugAgeAllCitizens`  

```csharp
public static System.Boolean s_DebugAgeAllCitizens;
```


## Constructors

- `public AgingSystem()`  

```csharp
public AgingSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetAdultAgeLimitInDays() : System.Int32`  

```csharp
public static System.Int32 GetAdultAgeLimitInDays();
```

- `public static GetElderAgeLimitInDays() : System.Int32`  

```csharp
public static System.Int32 GetElderAgeLimitInDays();
```

- `public static GetTeenAgeLimitInDays() : System.Int32`  

```csharp
public static System.Int32 GetTeenAgeLimitInDays();
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

- `Game.Simulation.AgingSystem+AgingJob`  
- `Game.Simulation.AgingSystem+TypeHandle`  

