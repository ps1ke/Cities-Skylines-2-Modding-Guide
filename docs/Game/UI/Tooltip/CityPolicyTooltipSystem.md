# Game.UI.Tooltip.CityPolicyTooltipSystem

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
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_ActiveInfomodeQuery`  
- `private Unity.Entities.Entity m_AdvancedPollutionManagementPolicy`  
- `private Game.UI.Tooltip.StringTooltip m_PollutionManagement`  
- `private Game.Common.RaycastResult m_RaycastResult`  

## Properties

- `private Game.Common.RaycastResult raycastResult { private get; private set }`  

## Constructors

- `public CityPolicyTooltipSystem()`  

## Methods

- `private IsAdvancedPollutionManagementEnabled() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

