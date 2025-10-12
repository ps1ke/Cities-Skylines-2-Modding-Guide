# Game.Simulation.PropertyRenterRemoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_RenterGroup`  
- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.PropertyRenterRemoveSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PropertyRenterRemoveSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PropertyRenterRemoveSystem+UpdateRentersJob`  
- `Game.Simulation.PropertyRenterRemoveSystem+RemoveData`  
- `Game.Simulation.PropertyRenterRemoveSystem+RemoveRentersJob`  
- `Game.Simulation.PropertyRenterRemoveSystem+TypeHandle`  

