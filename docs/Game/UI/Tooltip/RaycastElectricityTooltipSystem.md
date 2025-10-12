# Game.UI.Tooltip.RaycastElectricityTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultTool`  
- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  
- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private Game.UI.Tooltip.IntTooltip m_Production`  
- `private Game.UI.Tooltip.IntTooltip m_TransformerCapacity`  
- `private Game.UI.Tooltip.IntTooltip m_Usage`  
- `private Game.UI.Tooltip.IntTooltip m_BatteryFlow`  
- `private Game.UI.Tooltip.IntTooltip m_BatteryCharge`  
- `private Game.UI.Tooltip.ProgressTooltip m_Consumption`  
- `private Game.UI.Tooltip.ProgressTooltip m_Flow`  
- `private Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RaycastElectricityTooltipSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AddEdgeFlow(Unity.Entities.Entity edge, System.Single curvePosition) : System.Void`  
- `private AddNodeFlow(Unity.Entities.Entity node, Unity.Entities.Entity edge) : System.Void`  
- `private HasBottleneck(Unity.Entities.Entity building) : System.Boolean`  
- `private IsInfomodeActivated() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle`  

