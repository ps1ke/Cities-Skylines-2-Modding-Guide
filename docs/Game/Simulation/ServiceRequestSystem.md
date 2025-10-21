# Game.Simulation.ServiceRequestSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceRequestSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_RequestGroupQuery;
    private Unity.Entities.EntityQuery m_HandleRequestQuery;
    private Game.Simulation.ServiceRequestSystem+TypeHandle __TypeHandle;

    public ServiceRequestSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_RequestGroupQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequestGroupQuery;
```

- `private Unity.Entities.EntityQuery m_HandleRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_HandleRequestQuery;
```

- `private Game.Simulation.ServiceRequestSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ServiceRequestSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceRequestSystem()`  

```csharp
public ServiceRequestSystem();
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

- `Game.Simulation.ServiceRequestSystem+UpdateRequestGroupJob`  
- `Game.Simulation.ServiceRequestSystem+HandleRequestJob`  
- `Game.Simulation.ServiceRequestSystem+TypeHandle`  

