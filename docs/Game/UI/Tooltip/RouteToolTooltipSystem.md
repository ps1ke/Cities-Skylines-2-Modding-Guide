# Game.UI.Tooltip.RouteToolTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.RouteToolSystem m_RouteTool`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Game.UI.NameSystem m_NameSystem`  
- `private Unity.Entities.EntityQuery m_TempRouteQuery`  
- `private Unity.Entities.EntityQuery m_TempStopQuery`  
- `private Game.UI.Tooltip.NameTooltip m_StopName`  
- `private Game.UI.Tooltip.NameTooltip m_RouteName`  

## Constructors

- `public RouteToolTooltipSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public TryAddRouteName() : System.Void`  
- `public TryAddStopName() : System.Void`  

