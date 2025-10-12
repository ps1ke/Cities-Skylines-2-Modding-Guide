# Game.Simulation.AreaSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <debugFastSpawn>k__BackingField`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_AreaQuery`  
- `private Unity.Entities.EntityArchetype m_DefinitionArchetype`  
- `private Game.Simulation.AreaSpawnSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean debugFastSpawn { get; set }`  

## Constructors

- `public AreaSpawnSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AreaSpawnSystem+AreaSpawnJob`  
- `Game.Simulation.AreaSpawnSystem+TypeHandle`  

