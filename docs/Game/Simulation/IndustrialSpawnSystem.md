# Game.Simulation.IndustrialSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery`  
- `private Unity.Entities.EntityQuery m_StorageCompanyPrefabQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorCompanyQuery`  
- `private Unity.Entities.EntityQuery m_ExistingIndustrialQuery`  
- `private Unity.Entities.EntityQuery m_ExistingExtractorQuery`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.IndustrialSpawnSystem+TypeHandle __TypeHandle`  

## Constructors

- `public IndustrialSpawnSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.IndustrialSpawnSystem+CheckSpawnJob`  
- `Game.Simulation.IndustrialSpawnSystem+TypeHandle`  

