# Game.Routes.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
    private Game.Routes.InitializeSystem+TypeHandle __TypeHandle;

    public InitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  

```csharp
private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
```

- `private Game.Routes.InitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.InitializeSystem+TypeHandle __TypeHandle;
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

- `Game.Routes.InitializeSystem+AssignRouteNumbersJob`  
- `Game.Routes.InitializeSystem+SelectVehicleJob`  
- `Game.Routes.InitializeSystem+TypeHandle`  

