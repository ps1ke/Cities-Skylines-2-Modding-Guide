# Game.Triggers.EarlyGameOutsideConnectionTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.ResourceAvailabilitySystem m_ResourceAvailabilitySystem`  
- `private System.Boolean m_Started`  
- `private System.Double m_StartTime`  
- `private System.Boolean m_Triggered`  
- `private Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Single kDelaySeconds`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public EarlyGameOutsideConnectionTriggerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TriggerJob`  
- `Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle`  

