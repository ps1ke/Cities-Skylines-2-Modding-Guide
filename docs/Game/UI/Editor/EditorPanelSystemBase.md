# Game.UI.Editor.EditorPanelSystemBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Fields

- `private Game.UI.Editor.IEditorPanel m_LastSubPanel`  
- `private Game.UI.Editor.IEditorPanel <activeSubPanel>k__BackingField`  
- `private Game.UI.Localization.LocalizedString <title>k__BackingField`  
- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  
- `private readonly Colossal.Logging.ILog <log>k__BackingField`  

## Properties

- `protected Game.UI.Editor.IEditorPanel activeSubPanel { protected get; protected set }`  
- `protected Game.UI.Localization.LocalizedString title { protected get; protected set }`  
- `protected System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { protected get; protected set }`  
- `public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get }`  
- `protected Colossal.Logging.ILog log { protected get }`  
- `private Game.UI.Localization.LocalizedString Game.UI.Editor.IEditorPanel.title { private get }`  
- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> Game.UI.Editor.IEditorPanel.children { private get }`  

## Constructors

- `protected EditorPanelSystemBase()`  

## Methods

- `public CloseSubPanel() : System.Void`  
- `private Game.UI.Editor.IEditorPanel.OnCancel() : System.Boolean`  
- `private Game.UI.Editor.IEditorPanel.OnClose() : System.Boolean`  
- `private Game.UI.Editor.IEditorPanel.OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  
- `protected virtual OnCancel() : System.Boolean`  
- `protected virtual OnClose() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

