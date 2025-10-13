# Game.Simulation.LeaveHouseholdSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LeaveHouseholdSystem : Game.GameSystemBase
{
    private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_LeaveHouseholdQuery;
    private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.Simulation.LeaveHouseholdSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kNewHouseholdStartMoney;

    public LeaveHouseholdSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem`  

```csharp
private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_LeaveHouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeaveHouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.Simulation.LeaveHouseholdSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LeaveHouseholdSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kNewHouseholdStartMoney`  

```csharp
public static readonly System.Int32 kNewHouseholdStartMoney;
```


## Constructors

- `public LeaveHouseholdSystem()`  

```csharp
public LeaveHouseholdSystem();
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

- `Game.Simulation.LeaveHouseholdSystem+LeaveHouseholdJob`  
- `Game.Simulation.LeaveHouseholdSystem+TypeHandle`  

