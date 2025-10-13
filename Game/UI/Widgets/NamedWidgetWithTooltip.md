# Game.UI.Widgets.NamedWidgetWithTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class abstract public  

**Base:** `Game.UI.Widgets.NamedWidget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`  

## Code

```csharp
public abstract class NamedWidgetWithTooltip : Game.UI.Widgets.NamedWidget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider
{
    private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField;
    private System.String <uiTag>k__BackingField;

    public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set; }
    public System.String uiTag { get; set; }

    protected NamedWidgetWithTooltip();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField`  

```csharp
private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField;
```

- `private System.String <uiTag>k__BackingField`  

```csharp
private System.String <uiTag>k__BackingField;
```


## Properties

- `public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set }`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set; }
```

- `public System.String uiTag { get; set }`  

```csharp
public System.String uiTag { get; set; }
```


## Constructors

- `protected NamedWidgetWithTooltip()`  

```csharp
protected NamedWidgetWithTooltip();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("tooltip");
		writer.Write(tooltip);
		writer.PropertyName("uiTag");
		writer.Write(uiTag);
	}
```


