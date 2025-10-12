# Game.Simulation.HouseholdSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.HouseholdSpawnSystem+TypeHandle __TypeHandle`  

## Constructors

- `public HouseholdSpawnSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.HouseholdSpawnSystem+SpawnHouseholdJob`  
- `Game.Simulation.HouseholdSpawnSystem+TypeHandle`  

