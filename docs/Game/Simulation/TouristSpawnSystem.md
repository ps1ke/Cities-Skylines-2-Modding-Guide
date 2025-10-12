# Game.Simulation.TouristSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  
- `private Unity.Entities.EntityQuery m_AttractivenessParameterQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.TouristSpawnSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TouristSpawnSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TouristSpawnSystem+SpawnTouristHouseholdJob`  
- `Game.Simulation.TouristSpawnSystem+TypeHandle`  

