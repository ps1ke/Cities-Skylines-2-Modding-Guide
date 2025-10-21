# Game.Simulation.DispatchElectricitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DispatchElectricitySystem : Game.GameSystemBase
{
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_ConsumerQuery;
    private Game.Simulation.DispatchElectricitySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2129007938_0;
    private Unity.Entities.EntityQuery __query_2129007938_1;
    public static readonly System.Int16 kAlertCooldown;

    public DispatchElectricitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_ConsumerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerQuery;
```

- `private Game.Simulation.DispatchElectricitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DispatchElectricitySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2129007938_0`  

```csharp
private Unity.Entities.EntityQuery __query_2129007938_0;
```

- `private Unity.Entities.EntityQuery __query_2129007938_1`  

```csharp
private Unity.Entities.EntityQuery __query_2129007938_1;
```

- `public static readonly System.Int16 kAlertCooldown`  

```csharp
public static readonly System.Int16 kAlertCooldown;
```


## Constructors

- `public DispatchElectricitySystem()`  

```csharp
public DispatchElectricitySystem();
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

- `Game.Simulation.DispatchElectricitySystem+DispatchElectricityJob`  
- `Game.Simulation.DispatchElectricitySystem+TypeHandle`  

