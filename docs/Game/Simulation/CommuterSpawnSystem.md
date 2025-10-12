# Game.Simulation.CommuterSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  
- `private Unity.Entities.EntityQuery m_CommuterQuery`  
- `private Unity.Entities.EntityQuery m_WorkerQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  
- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  
- `private Game.Simulation.CommuterSpawnSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CommuterSpawnSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CommuterSpawnSystem+SpawnCommuterHouseholdJob`  
- `Game.Simulation.CommuterSpawnSystem+TypeHandle`  

