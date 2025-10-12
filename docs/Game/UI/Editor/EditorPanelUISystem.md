# Game.UI.Editor.EditorPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.UI.Editor.IEditorPanel m_LastPanel`  
- `private Game.UI.Editor.IEditorPanel <activePanel>k__BackingField`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Localization.LocalizedString>> m_TitleBinding`  
- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `public Game.UI.Editor.IEditorPanel activePanel { get; set }`  
- `private Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { private get }`  

## Constructors

- `public EditorPanelUISystem()`  

## Methods

- `private <OnCreate>b__13_0() : System.Int32`  
- `public static AddEditorWidgetBindings(Game.UI.Widgets.WidgetBindings widgetBindings) : System.Void`  
- `private Cancel() : System.Void`  
- `private Close() : System.Void`  
- `private GetWidth() : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  
- `private SetWidth(System.Int32 width) : System.Void`  

