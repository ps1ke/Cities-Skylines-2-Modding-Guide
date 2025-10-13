# Game.Serialization.RouteVehicleSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteVehicleSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.RouteVehicleSystem+TypeHandle __TypeHandle;

    public RouteVehicleSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.RouteVehicleSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.RouteVehicleSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteVehicleSystem()`  

```csharp
public RouteVehicleSystem();
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

- `Game.Serialization.RouteVehicleSystem+RouteVehicleJob`  
- `Game.Serialization.RouteVehicleSystem+TypeHandle`  

