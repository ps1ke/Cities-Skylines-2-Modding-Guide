# Game.Buildings.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  
- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  
- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  
- `private Unity.Entities.EntityQuery m_CoverageQuery`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents`  
- `private Game.Buildings.InitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public InitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Buildings.InitializeSystem+InitializeCoverageTypeJob`  
- `Game.Buildings.InitializeSystem+InitializeBuildingsJob`  
- `Game.Buildings.InitializeSystem+TypeHandle`  

