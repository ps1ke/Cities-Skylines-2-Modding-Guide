# Game.Simulation.UtilityFeeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  
- `private Unity.Entities.EntityQuery m_ConsumerGroup`  
- `private Game.Simulation.UtilityFeeSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 kUpdatesPerDay`  

## Constructors

- `public UtilityFeeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.UtilityFeeSystem+SellUtilitiesJob`  
- `Game.Simulation.UtilityFeeSystem+TypeHandle`  

