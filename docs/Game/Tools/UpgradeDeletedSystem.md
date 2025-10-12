# Game.Tools.UpgradeDeletedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_DeletedQuery`  
- `private Game.Tools.UpgradeDeletedSystem+TypeHandle __TypeHandle`  

## Constructors

- `public UpgradeDeletedSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.UpgradeDeletedSystem+UpgradeDeletedJob`  
- `Game.Tools.UpgradeDeletedSystem+TypeHandle`  

