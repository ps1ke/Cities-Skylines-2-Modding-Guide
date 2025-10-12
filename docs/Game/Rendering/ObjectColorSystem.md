# Game.Rendering.ObjectColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ObjectQuery`  
- `private Unity.Entities.EntityQuery m_MiddleObjectQuery`  
- `private Unity.Entities.EntityQuery m_TempObjectQuery`  
- `private Unity.Entities.EntityQuery m_SubObjectQuery`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  
- `private Unity.Entities.EntityQuery m_FireConfigQuery`  
- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.FireHazardSystem m_FireHazardSystem`  
- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.ObjectColorSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ObjectColorSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.ObjectColorSystem+UpdateObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateMiddleObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateTempObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateSubObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+TypeHandle`  

