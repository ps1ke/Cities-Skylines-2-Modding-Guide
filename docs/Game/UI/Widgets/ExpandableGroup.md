# Game.UI.Widgets.ExpandableGroup

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidgetWithTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IExpandable`, `Game.UI.Widgets.IContainerWidget`  

## Fields

- `private Game.Reflection.ITypedValueAccessor<System.Boolean> m_ExpandedAccessor`  
- `private System.Boolean m_Expanded`  
- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children`  

## Properties

- `public System.Boolean expanded { get; set }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

## Constructors

- `public ExpandableGroup(Game.Reflection.ITypedValueAccessor<System.Boolean> expandedAccessor)`  
- `public ExpandableGroup(System.Boolean expanded = False)`  

## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

