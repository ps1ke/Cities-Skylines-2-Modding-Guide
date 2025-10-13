# Game.Routes.RoutePathReadySystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoutePathReadySystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_PathReadyQuery;
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Unity.Entities.EntityQuery m_RouteConfigQuery;
    private System.Boolean m_Loaded;
    private Game.Routes.RoutePathReadySystem+TypeHandle __TypeHandle;

    public RoutePathReadySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_PathReadyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PathReadyQuery;
```

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteConfigQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Routes.RoutePathReadySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.RoutePathReadySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RoutePathReadySystem()`  

```csharp
public RoutePathReadySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Routes.RoutePathReadySystem+RoutePathReadyJob`  
- `Game.Routes.RoutePathReadySystem+TypeHandle`  

