# Game.Simulation.DispatchWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DispatchWaterSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_ConsumerQuery;
    private System.Boolean <freshConsumptionDisabled>k__BackingField;
    private System.Boolean <sewageConsumptionDisabled>k__BackingField;
    private Game.Simulation.DispatchWaterSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1010455350_0;
    private Unity.Entities.EntityQuery __query_1010455350_1;
    public static readonly System.Int16 kAlertCooldown;
    public static readonly System.Int16 kHealthPenaltyCooldown;
    private static const System.Single kNotificationMaxDelay;

    public System.Boolean freshConsumptionDisabled { get; set; }
    public System.Boolean sewageConsumptionDisabled { get; set; }

    public DispatchWaterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_ConsumerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerQuery;
```

- `private System.Boolean <freshConsumptionDisabled>k__BackingField`  

```csharp
private System.Boolean <freshConsumptionDisabled>k__BackingField;
```

- `private System.Boolean <sewageConsumptionDisabled>k__BackingField`  

```csharp
private System.Boolean <sewageConsumptionDisabled>k__BackingField;
```

- `private Game.Simulation.DispatchWaterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DispatchWaterSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1010455350_0`  

```csharp
private Unity.Entities.EntityQuery __query_1010455350_0;
```

- `private Unity.Entities.EntityQuery __query_1010455350_1`  

```csharp
private Unity.Entities.EntityQuery __query_1010455350_1;
```

- `public static readonly System.Int16 kAlertCooldown`  

```csharp
public static readonly System.Int16 kAlertCooldown;
```

- `public static readonly System.Int16 kHealthPenaltyCooldown`  

```csharp
public static readonly System.Int16 kHealthPenaltyCooldown;
```

- `private static const System.Single kNotificationMaxDelay`  

```csharp
private static const System.Single kNotificationMaxDelay;
```


## Properties

- `public System.Boolean freshConsumptionDisabled { get; set }`  

```csharp
public System.Boolean freshConsumptionDisabled { get; set; }
```

- `public System.Boolean sewageConsumptionDisabled { get; set }`  

```csharp
public System.Boolean sewageConsumptionDisabled { get; set; }
```


## Constructors

- `public DispatchWaterSystem()`  

```csharp
public DispatchWaterSystem();
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

- `Game.Simulation.DispatchWaterSystem+DispatchWaterJob`  
- `Game.Simulation.DispatchWaterSystem+TypeHandle`  

