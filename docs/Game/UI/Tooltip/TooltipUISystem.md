# Game.UI.Tooltip.TooltipUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.UpdateSystem m_UpdateSystem`  
- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  
- `private System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> <groups>k__BackingField`  
- `private Game.UI.Tooltip.TooltipGroup <mouseGroup>k__BackingField`  
- `private static readonly Unity.Mathematics.float2 kTooltipPointerDistance`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `public System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> groups { get; private set }`  
- `public Game.UI.Tooltip.TooltipGroup mouseGroup { get; private set }`  

## Constructors

- `public TooltipUISystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

