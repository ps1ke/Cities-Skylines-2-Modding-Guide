# Game.UI.Widgets.WidgetBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget>`  

## Fields

- `private System.String m_Group`  
- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_LastChildren`  
- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  
- `private System.Collections.Generic.List<System.Int32> m_CurrentPath`  
- `private Colossal.UI.Binding.RawValueBinding m_ChildrenBinding`  
- `private Game.UI.Widgets.ValueChangedCallback EventValueChanged`  

## Properties

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  
- `public System.Boolean active { get }`  

## Constructors

- `public WidgetBindings(System.String group, System.String name = children)`  

## Methods

- `public AddBindings<U>() : System.Void`  
- `public AddBindings(Game.UI.Widgets.IWidgetBindingFactory bindingFactory) : System.Void`  
- `public AddDefaultBindings() : System.Void`  
- `private Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget>.Read(Colossal.UI.Binding.IJsonReader reader, Game.UI.Widgets.IWidget& value) : System.Void`  
- `private OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  
- `public virtual Update() : System.Boolean`  
- `private UpdateChildrenBinding() : System.Void`  
- `private UpdateSubTree(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> widgets, System.Boolean patch) : System.Boolean`  
- `private WriteChildren(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Events

- `EventValueChanged` : `Game.UI.Widgets.ValueChangedCallback`  

