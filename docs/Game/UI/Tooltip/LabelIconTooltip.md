# Game.UI.Tooltip.LabelIconTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class abstract public  

**Base:** `Game.UI.Tooltip.IconTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public abstract class LabelIconTooltip : Game.UI.Tooltip.IconTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Game.UI.Localization.LocalizedString m_Label;

    public Game.UI.Localization.LocalizedString label { get; set; }

    protected LabelIconTooltip();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.UI.Localization.LocalizedString m_Label`  

```csharp
private Game.UI.Localization.LocalizedString m_Label;
```


## Properties

- `public Game.UI.Localization.LocalizedString label { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString label { get; set; }
```


## Constructors

- `protected LabelIconTooltip()`  

```csharp
protected LabelIconTooltip();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


