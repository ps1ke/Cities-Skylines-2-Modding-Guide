# Game.UI.Tooltip.RaycastWaterTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultTool`  
- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  
- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private Game.UI.Tooltip.IntTooltip m_WaterCapacity`  
- `private Game.UI.Tooltip.IntTooltip m_WaterUsage`  
- `private Game.UI.Tooltip.IntTooltip m_SewageCapacity`  
- `private Game.UI.Tooltip.IntTooltip m_SewageUsage`  
- `private Game.UI.Tooltip.ProgressTooltip m_WaterConsumption`  
- `private Game.UI.Tooltip.ProgressTooltip m_SewageConsumption`  
- `private Game.UI.Tooltip.IntTooltip m_WaterFlow`  
- `private Game.UI.Tooltip.IntTooltip m_SewageFlow`  
- `private Game.UI.Tooltip.RaycastWaterTooltipSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RaycastWaterTooltipSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AddEdgeFlow(Unity.Entities.Entity edge, System.Single curvePosition) : System.Void`  
- `private AddNodeFlow(Unity.Entities.Entity node, Unity.Entities.Entity edge) : System.Void`  
- `private IsInfomodeActivated() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.UI.Tooltip.RaycastWaterTooltipSystem+TypeHandle`  

