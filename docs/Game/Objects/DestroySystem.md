# Game.Objects.DestroySystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  
- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  
- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityQuery m_BuildingConfigurationQuery`  
- `private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents`  
- `private Game.Objects.DestroySystem+TypeHandle __TypeHandle`  

## Constructors

- `public DestroySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Objects.DestroySystem+DestroyObjectsJob`  
- `Game.Objects.DestroySystem+TypeHandle`  

