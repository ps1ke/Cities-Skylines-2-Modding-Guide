# Game.UI.Tooltip.StringTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.IconTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class StringTooltip : Game.UI.Tooltip.IconTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Game.UI.Localization.LocalizedString m_Value;

    public Game.UI.Localization.LocalizedString value { get; set; }

    public StringTooltip();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.UI.Localization.LocalizedString m_Value`  

```csharp
private Game.UI.Localization.LocalizedString m_Value;
```


## Properties

- `public Game.UI.Localization.LocalizedString value { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString value { get; set; }
```


## Constructors

- `public StringTooltip()`  

```csharp
public StringTooltip();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


