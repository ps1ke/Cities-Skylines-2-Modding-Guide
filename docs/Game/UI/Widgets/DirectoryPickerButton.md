# Game.UI.Widgets.DirectoryPickerButton

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidgetWithTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IInvokable`  

## Code

```csharp
public class DirectoryPickerButton : Game.UI.Widgets.NamedWidgetWithTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.IInvokable
{
    private System.String m_SelectedDirectory;
    private System.String <displayValue>k__BackingField;
    private System.Action <action>k__BackingField;

    public System.String displayValue { get; set; }
    public System.Action action { get; set; }
    public System.String propertiesTypeName { get; }

    public DirectoryPickerButton();

    public System.Void Invoke();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String m_SelectedDirectory`  

```csharp
private System.String m_SelectedDirectory;
```

- `private System.String <displayValue>k__BackingField`  

```csharp
private System.String <displayValue>k__BackingField;
```

- `private System.Action <action>k__BackingField`  

```csharp
private System.Action <action>k__BackingField;
```


## Properties

- `public System.String displayValue { get; set }`  

```csharp
public System.String displayValue { get; set; }
```

- `public System.Action action { get; set }`  

```csharp
public System.Action action { get; set; }
```

- `public System.String propertiesTypeName { get }`  

```csharp
public System.String propertiesTypeName { get; }
```


## Constructors

- `public DirectoryPickerButton()`  

```csharp
public DirectoryPickerButton();
```


## Methods

- `public Invoke() : System.Void`  

```csharp
public System.Void Invoke();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


