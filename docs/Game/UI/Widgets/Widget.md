# Game.UI.Widgets.Widget

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `private Game.UI.Widgets.WidgetChanges m_Changes`  
- `private Game.UI.Widgets.PathSegment m_Path`  
- `private System.String m_TutorialTag`  
- `protected System.Boolean m_Disabled`  
- `protected System.Boolean m_Hidden`  
- `private System.Boolean m_IsInitialUpdate`  
- `private System.Func<System.Boolean> <disabled>k__BackingField`  
- `private System.Func<System.Boolean> <hidden>k__BackingField`  
- `protected static const System.String kProperties`  
- `protected static const System.String kChildren`  
- `protected static const System.String kTutorialTag`  

## Properties

- `public Game.UI.Widgets.PathSegment path { get; set }`  
- `public System.String tutorialTag { get; set }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  
- `public System.Func<System.Boolean> disabled { get; set }`  
- `public System.Func<System.Boolean> hidden { get; set }`  
- `public System.Boolean isVisible { get }`  
- `public System.Boolean isActive { get }`  
- `public System.String propertiesTypeName { get }`  

## Constructors

- `protected Widget()`  

## Methods

- `private Game.UI.Widgets.IWidget.Update() : Game.UI.Widgets.WidgetChanges`  
- `private Game.UI.Widgets.IWidget.WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public static PatchWidget(Colossal.UI.Binding.RawValueBinding binding, System.Collections.Generic.IList<System.Int32> path, Game.UI.Widgets.IWidget widget, Game.UI.Widgets.WidgetChanges changes) : System.Void`  
- `public SetChildrenChanged() : System.Void`  
- `public SetPropertiesChanged() : System.Void`  
- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `private UpdateBase() : Game.UI.Widgets.WidgetChanges`  
- `public virtual UpdateVisibility() : Game.UI.Widgets.WidgetChanges`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteBaseProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path) : System.Void`  
- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName) : System.Void`  
- `public static WritePatchPath(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.Int32> path, System.String propertyName1, System.String propertyName2, System.String propertyName3, System.Int32 propertyName4) : System.Void`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

