# Game.Simulation.ZoneSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <debugFastSpawn>k__BackingField`  
- `private Game.Prefabs.ZoneSystem m_ZoneSystem`  
- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  
- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  
- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  
- `private Game.Simulation.GroundPollutionSystem m_PollutionSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Zones.SearchSystem m_SearchSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_LotQuery`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_ProcessQuery`  
- `private Unity.Entities.EntityQuery m_BuildingConfigurationQuery`  
- `private Unity.Entities.EntityArchetype m_DefinitionArchetype`  
- `private Game.Simulation.ZoneSpawnSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1944910157_0`  

## Properties

- `public System.Boolean debugFastSpawn { get; set }`  

## Constructors

- `public ZoneSpawnSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ZoneSpawnSystem+SpawnLocation`  
- `Game.Simulation.ZoneSpawnSystem+EvaluateSpawnAreas`  
- `Game.Simulation.ZoneSpawnSystem+SpawnBuildingJob`  
- `Game.Simulation.ZoneSpawnSystem+TypeHandle`  

