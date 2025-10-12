# Game.Simulation.UpdateGroupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_CreatedQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes`  
- `private Game.Simulation.UpdateGroupSystem+UpdateGroupSizes m_UpdateGroupSizes`  
- `private Game.Simulation.UpdateGroupSystem+TypeHandle __TypeHandle`  

## Constructors

- `public UpdateGroupSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetUpdateGroupSizes() : Game.Simulation.UpdateGroupSystem+UpdateGroupSizes`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.UpdateGroupSystem+UpdateGroupTypes`  
- `Game.Simulation.UpdateGroupSystem+UpdateGroupSizes`  
- `Game.Simulation.UpdateGroupSystem+UpdateGroupJob`  
- `Game.Simulation.UpdateGroupSystem+MovingObjectsUpdatedJob`  
- `Game.Simulation.UpdateGroupSystem+TypeHandle`  

