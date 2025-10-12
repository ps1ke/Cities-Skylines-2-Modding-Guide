# Game.Simulation.CitizenTravelPurposeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_ArrivedGroup`  
- `private Unity.Entities.EntityQuery m_StuckGroup`  
- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  
- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  
- `private Game.Simulation.CitizenTravelPurposeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CitizenTravelPurposeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CitizenTravelPurposeSystem+CitizenArriveJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+Arrive`  
- `Game.Simulation.CitizenTravelPurposeSystem+ArriveType`  
- `Game.Simulation.CitizenTravelPurposeSystem+ArriveJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+CitizenStuckJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+TypeHandle`  

