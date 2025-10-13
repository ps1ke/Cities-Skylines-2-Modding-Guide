# Game.Simulation.ServiceCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceCompanySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
    private Unity.Entities.EntityQuery m_BuildingParameterQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.ServiceCompanySystem+TypeHandle __TypeHandle;

    public ServiceCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingParameterQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.ServiceCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ServiceCompanySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceCompanySystem()`  

```csharp
public ServiceCompanySystem();
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

- `Game.Simulation.ServiceCompanySystem+UpdateServiceJob`  
- `Game.Simulation.ServiceCompanySystem+TypeHandle`  

