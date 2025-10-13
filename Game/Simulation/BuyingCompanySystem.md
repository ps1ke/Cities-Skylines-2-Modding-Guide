# Game.Simulation.BuyingCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuyingCompanySystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Game.Simulation.BuyingCompanySystem+TypeHandle __TypeHandle;
    private static readonly System.Single kNotificationCostLimit;
    private static readonly System.Int32 kResourceLowStockAmount;
    private static readonly System.Int32 kResourceMinimumRequestAmount;

    public BuyingCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Game.Simulation.BuyingCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BuyingCompanySystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single kNotificationCostLimit`  

```csharp
private static readonly System.Single kNotificationCostLimit;
```

- `private static readonly System.Int32 kResourceLowStockAmount`  

```csharp
private static readonly System.Int32 kResourceLowStockAmount;
```

- `private static readonly System.Int32 kResourceMinimumRequestAmount`  

```csharp
private static readonly System.Int32 kResourceMinimumRequestAmount;
```


## Constructors

- `public BuyingCompanySystem()`  

```csharp
public BuyingCompanySystem();
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

- `Game.Simulation.BuyingCompanySystem+CompanyBuyJob`  
- `Game.Simulation.BuyingCompanySystem+TypeHandle`  

