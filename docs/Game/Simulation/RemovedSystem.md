# Game.Simulation.RemovedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RemovedSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_DeletedBuildings;
    private Unity.Entities.EntityQuery m_DeletedWorkplaces;
    private Unity.Entities.EntityQuery m_DeletedCompanies;
    private Unity.Entities.EntityQuery m_NeedUpdateRenterQuery;
    private Unity.Entities.EntityQuery m_BuildingParameterQuery;
    private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Simulation.RemovedSystem+TypeHandle __TypeHandle;

    public RemovedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DeletedBuildings`  

```csharp
private Unity.Entities.EntityQuery m_DeletedBuildings;
```

- `private Unity.Entities.EntityQuery m_DeletedWorkplaces`  

```csharp
private Unity.Entities.EntityQuery m_DeletedWorkplaces;
```

- `private Unity.Entities.EntityQuery m_DeletedCompanies`  

```csharp
private Unity.Entities.EntityQuery m_DeletedCompanies;
```

- `private Unity.Entities.EntityQuery m_NeedUpdateRenterQuery`  

```csharp
private Unity.Entities.EntityQuery m_NeedUpdateRenterQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Simulation.RemovedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.RemovedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RemovedSystem()`  

```csharp
public RemovedSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Simulation.RemovedSystem+RemovedPropertyJob`  
- `Game.Simulation.RemovedSystem+RemovedWorkplaceJob`  
- `Game.Simulation.RemovedSystem+RemovedCompanyJob`  
- `Game.Simulation.RemovedSystem+RentersUpdateJob`  
- `Game.Simulation.RemovedSystem+TypeHandle`  

