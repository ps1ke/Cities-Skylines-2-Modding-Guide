# Game.UI.Menu.DirectoryPickerField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<System.String>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IInvokable`, `Game.UI.Widgets.IWarning`  

## Code

```csharp
public class DirectoryPickerField : Game.UI.Widgets.Field<System.String>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IInvokable, Game.UI.Widgets.IWarning
{
    private System.Boolean m_Warning;
    private System.Func<System.Boolean> <warningAction>k__BackingField;
    private System.Action <action>k__BackingField;

    public System.Func<System.Boolean> warningAction { get; set; }
    public System.String propertiesTypeName { get; }
    public System.Action action { get; set; }
    public System.Boolean warning { get; set; }

    public DirectoryPickerField();

    public System.Void Invoke();
    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean m_Warning`  

```csharp
private System.Boolean m_Warning;
```

- `private System.Func<System.Boolean> <warningAction>k__BackingField`  

```csharp
private System.Func<System.Boolean> <warningAction>k__BackingField;
```

- `private System.Action <action>k__BackingField`  

```csharp
private System.Action <action>k__BackingField;
```


## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  

```csharp
public System.Func<System.Boolean> warningAction { get; set; }
```

- `public System.String propertiesTypeName { get }`  

```csharp
public System.String propertiesTypeName { get; }
```

- `public System.Action action { get; set }`  

```csharp
public System.Action action { get; set; }
```

- `public System.Boolean warning { get; set }`  

```csharp
public System.Boolean warning { get; set; }
```


## Constructors

- `public DirectoryPickerField()`  

```csharp
public DirectoryPickerField();
```


## Methods

- `public Invoke() : System.Void`  

```csharp
public System.Void Invoke();
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


