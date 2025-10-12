# Game.UI.Menu.DirectoryPickerField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<System.String>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IInvokable`, `Game.UI.Widgets.IWarning`  

## Fields

- `private System.Boolean m_Warning`  
- `private System.Func<System.Boolean> <warningAction>k__BackingField`  
- `private System.Action <action>k__BackingField`  

## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  
- `public System.String propertiesTypeName { get }`  
- `public System.Action action { get; set }`  
- `public System.Boolean warning { get; set }`  

## Constructors

- `public DirectoryPickerField()`  

## Methods

- `public Invoke() : System.Void`  
- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

