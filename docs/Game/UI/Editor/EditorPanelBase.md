# Game.UI.Editor.EditorPanelBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Fields

- `private Game.UI.Localization.LocalizedString <title>k__BackingField`  
- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

## Properties

- `public Game.UI.Localization.LocalizedString title { get; set }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  
- `public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get }`  

## Constructors

- `protected EditorPanelBase()`  

## Methods

- `public virtual OnCancel() : System.Boolean`  
- `public virtual OnClose() : System.Boolean`  
- `public virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

