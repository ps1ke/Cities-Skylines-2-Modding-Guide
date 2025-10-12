# Game.Simulation.ElectricityStatusSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_EdgeQuery`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_ElectricityParameterQuery`  
- `private Game.Simulation.ElectricityStatusSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ElectricityStatusSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ElectricityStatusSystem+NetEdgeNotificationJob`  
- `Game.Simulation.ElectricityStatusSystem+BuildingNotificationJob`  
- `Game.Simulation.ElectricityStatusSystem+TypeHandle`  

