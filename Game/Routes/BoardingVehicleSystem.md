# Game.Routes.BoardingVehicleSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BoardingVehicleSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_WaypointQuery;
    private Unity.Entities.EntityQuery m_BoardingQuery;
    private System.Boolean m_Loaded;
    private Game.Routes.BoardingVehicleSystem+TypeHandle __TypeHandle;

    public BoardingVehicleSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_WaypointQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaypointQuery;
```

- `private Unity.Entities.EntityQuery m_BoardingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BoardingQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Routes.BoardingVehicleSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.BoardingVehicleSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BoardingVehicleSystem()`  

```csharp
public BoardingVehicleSystem();
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

- `Game.Routes.BoardingVehicleSystem+BoardingVehicleJob`  
- `Game.Routes.BoardingVehicleSystem+TypeHandle`  

