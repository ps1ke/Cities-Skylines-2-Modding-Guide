# Game.Policies.RouteModifierInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteModifierInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData;
    private Game.Policies.RouteModifierInitializeSystem+TypeHandle __TypeHandle;

    public RouteModifierInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData`  

```csharp
private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData;
```

- `private Game.Policies.RouteModifierInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.RouteModifierInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteModifierInitializeSystem()`  

```csharp
public RouteModifierInitializeSystem();
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

- `Game.Policies.RouteModifierInitializeSystem+InitializeRouteModifiersJob`  
- `Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData`  
- `Game.Policies.RouteModifierInitializeSystem+TypeHandle`  

