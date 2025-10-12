# Game.Simulation.BuildingConstructionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.ZoneSpawnSystem m_ZoneSpawnSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Game.Simulation.BuildingConstructionSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 UPDATE_INTERVAL_BITS`  
- `public static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public BuildingConstructionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.BuildingConstructionSystem+BuildingConstructionJob`  
- `Game.Simulation.BuildingConstructionSystem+TypeHandle`  

