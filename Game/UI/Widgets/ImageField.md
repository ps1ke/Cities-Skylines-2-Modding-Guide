# Game.UI.Widgets.ImageField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.ITooltipTarget`  

## Code

```csharp
public class ImageField : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.ITooltipTarget
{
    private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField;
    public System.String m_URI;
    public Game.UI.Localization.LocalizedString m_Label;

    public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set; }

    public ImageField();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField`  

```csharp
private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField;
```

- `public System.String m_URI`  

```csharp
public System.String m_URI;
```

- `public Game.UI.Localization.LocalizedString m_Label`  

```csharp
public Game.UI.Localization.LocalizedString m_Label;
```


## Properties

- `public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set }`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set; }
```


## Constructors

- `public ImageField()`  

```csharp
public ImageField();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("uri");
		writer.Write(m_URI);
		writer.PropertyName("label");
		writer.Write(m_Label);
		writer.PropertyName("tooltip");
		writer.Write(tooltip);
	}
```


