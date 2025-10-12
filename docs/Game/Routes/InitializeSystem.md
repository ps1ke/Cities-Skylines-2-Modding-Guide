# Game.Routes.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_CreatedQuery`  
- `private Unity.Entities.EntityQuery m_RouteQuery`  
- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  
- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  
- `private Game.Routes.InitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public InitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Routes.InitializeSystem+AssignRouteNumbersJob`  
- `Game.Routes.InitializeSystem+SelectVehicleJob`  
- `Game.Routes.InitializeSystem+TypeHandle`  

