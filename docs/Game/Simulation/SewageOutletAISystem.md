# Game.Simulation.SewageOutletAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SewageOutletAISystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_OutletQuery;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.Simulation.SewageOutletAISystem+TypeHandle __TypeHandle;

    public SewageOutletAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_OutletQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutletQuery;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.Simulation.SewageOutletAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.SewageOutletAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SewageOutletAISystem()`  

```csharp
public SewageOutletAISystem();
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

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.SewageOutletAISystem+OutletTickJob`  
- `Game.Simulation.SewageOutletAISystem+TypeHandle`  

