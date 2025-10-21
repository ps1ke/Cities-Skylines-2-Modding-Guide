# Game.Simulation.BatteryAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatteryAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BatteryQuery;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.BatteryAISystem+TypeHandle __TypeHandle;

    public BatteryAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BatteryQuery`  

```csharp
private Unity.Entities.EntityQuery m_BatteryQuery;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.BatteryAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BatteryAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BatteryAISystem()`  

```csharp
public BatteryAISystem();
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

- `Game.Simulation.BatteryAISystem+BatteryTickJob`  
- `Game.Simulation.BatteryAISystem+TypeHandle`  

