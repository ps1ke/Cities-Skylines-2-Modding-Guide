# Game.Simulation.AircraftNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Net.AirwaySystem m_AirwaySystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  
- `private Game.Simulation.AircraftNavigationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AircraftNavigationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AircraftNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.AircraftNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.AircraftNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.AircraftNavigationSystem+TypeHandle`  

