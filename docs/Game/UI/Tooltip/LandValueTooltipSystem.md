# Game.UI.Tooltip.LandValueTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.RaycastSystem m_RaycastSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.TerrainToolSystem m_TerrainToolSystem`  
- `private Game.Simulation.LandValueSystem m_LandValueSystem`  
- `private Game.Debug.LandValueDebugSystem m_LandValueDebugSystem`  
- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `private Unity.Entities.EntityQuery m_AttractivenessParameterQuery`  
- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  
- `private Game.UI.Tooltip.FloatTooltip m_LandValueTooltip`  
- `private Game.UI.Tooltip.FloatTooltip m_TerrainAttractiveTooltip`  
- `private Game.UI.Tooltip.FloatTooltip m_AirPollutionTooltip`  
- `private Game.UI.Tooltip.FloatTooltip m_GroundPollutionTooltip`  
- `private Game.UI.Tooltip.FloatTooltip m_NoisePollutionTooltip`  
- `private Colossal.Collections.NativeValue<System.Single> m_LandValueResult`  
- `private Colossal.Collections.NativeValue<System.Single> m_TerrainAttractiveResult`  
- `private Colossal.Collections.NativeValue<System.Single> m_AirPollutionResult`  
- `private Colossal.Collections.NativeValue<System.Single> m_NoisePollutionResult`  
- `private Colossal.Collections.NativeValue<System.Single> m_GroundPollutionResult`  

## Constructors

- `public LandValueTooltipSystem()`  

## Methods

- `private IsInfomodeActivated() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.UI.Tooltip.LandValueTooltipSystem+LandValueTooltipJob`  

