# Game.Simulation.PersonalCarAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  
- `private Game.Simulation.PersonalCarAISystem+Actions m_Actions`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedCarAddTypes`  
- `private Game.Simulation.PersonalCarAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public PersonalCarAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PersonalCarAISystem+Actions`  
- `Game.Simulation.PersonalCarAISystem+MoneyTransfer`  
- `Game.Simulation.PersonalCarAISystem+PersonalCarTickJob`  
- `Game.Simulation.PersonalCarAISystem+TransferMoneyJob`  
- `Game.Simulation.PersonalCarAISystem+TypeHandle`  

