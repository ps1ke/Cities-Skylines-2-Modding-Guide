# Game.UI.Tooltip.PollutionTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultTool`  
- `private Game.Common.RaycastSystem m_RaycastSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_ActiveInfomodeQuery`  
- `private Game.UI.Tooltip.IntTooltip m_Garbage`  
- `private Game.UI.Tooltip.IntTooltip m_AirPollution`  
- `private Game.UI.Tooltip.IntTooltip m_GroundPollution`  
- `private Game.UI.Tooltip.IntTooltip m_NoisePollution`  
- `private Game.UI.Tooltip.IntTooltip m_WaterPollution`  
- `private Game.Common.RaycastResult m_RaycastResult`  

## Properties

- `private Game.Common.RaycastResult raycastResult { private get; private set }`  

## Constructors

- `public PollutionTooltipSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

