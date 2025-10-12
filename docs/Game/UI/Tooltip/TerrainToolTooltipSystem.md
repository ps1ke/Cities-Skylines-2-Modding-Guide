# Game.UI.Tooltip.TerrainToolTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.TerrainToolSystem m_TerrainTool`  
- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Unity.Entities.EntityQuery m_ParameterQuery`  
- `private Game.UI.Tooltip.IntTooltip m_GroundwaterVolume`  
- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult`  

## Constructors

- `public TerrainToolTooltipSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ProcessResults() : System.Void`  

