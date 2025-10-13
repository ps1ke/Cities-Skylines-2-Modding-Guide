# Game.Vehicles.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSystem : Game.GameSystemBase
{
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Vehicles.InitializeSystem+TypeHandle __TypeHandle;

    public InitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Vehicles.InitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Vehicles.InitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeSystem()`  

```csharp
public InitializeSystem();
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

- `Game.Vehicles.InitializeSystem+TreeFixJob`  
- `Game.Vehicles.InitializeSystem+InitializeVehiclesJob`  
- `Game.Vehicles.InitializeSystem+TypeHandle`  

