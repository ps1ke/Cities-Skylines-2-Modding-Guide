# Game.Simulation.GarbageTruckAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Unity.Entities.EntityArchetype m_GarbageCollectionRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes`  
- `private Game.Simulation.GarbageTruckAISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_647374864_0`  
- `private Unity.Entities.EntityQuery __query_647374864_1`  

## Constructors

- `public GarbageTruckAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.GarbageTruckAISystem+GarbageActionType`  
- `Game.Simulation.GarbageTruckAISystem+GarbageAction`  
- `Game.Simulation.GarbageTruckAISystem+GarbageTruckTickJob`  
- `Game.Simulation.GarbageTruckAISystem+GarbageActionJob`  
- `Game.Simulation.GarbageTruckAISystem+TypeHandle`  

