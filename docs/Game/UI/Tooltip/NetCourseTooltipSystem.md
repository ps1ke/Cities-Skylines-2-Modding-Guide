# Game.UI.Tooltip.NetCourseTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.NetToolSystem m_NetTool`  
- `private Unity.Entities.EntityQuery m_NetCourseQuery`  
- `private Game.UI.Tooltip.TooltipGroup m_Group`  
- `private Game.UI.Tooltip.FloatTooltip m_Length`  
- `private Game.UI.Tooltip.FloatTooltip m_Slope`  
- `private Game.UI.Tooltip.NetCourseTooltipSystem+TypeHandle __TypeHandle`  
- `private static const System.Single kMinLength`  

## Constructors

- `public NetCourseTooltipSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static GetWorldPosition(Unity.Collections.NativeList<Game.Tools.NetCourse> courses, System.Single length) : Unity.Mathematics.float3`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private static SortCourses(Unity.Collections.NativeList<Game.Tools.NetCourse> courses) : System.Void`  

## Nested types

- `Game.UI.Tooltip.NetCourseTooltipSystem+TypeHandle`  

