# Game.Simulation.AreaLotSimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_Watersystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_AreaQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorQuery`  
- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  
- `private Game.Prefabs.WorkVehicleSelectData m_WorkVehicleSelectData`  
- `private Game.Simulation.AreaLotSimulationSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public AreaLotSimulationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetUnlimitedTotalAmount(System.Int32 used, System.Int32 originalAmount, System.Single mu) : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AreaLotSimulationSystem+ManageVehiclesJob`  
- `Game.Simulation.AreaLotSimulationSystem+ExtractResourcesJob`  
- `Game.Simulation.AreaLotSimulationSystem+TypeHandle`  

