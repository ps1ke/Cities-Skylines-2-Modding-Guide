# Game.UI.Tooltip.IconTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class abstract public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public abstract class IconTooltip : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private System.String m_Icon;
    private Game.UI.Tooltip.TooltipColor m_Color;

    public System.String icon { get; set; }
    public Game.UI.Tooltip.TooltipColor color { get; set; }

    protected IconTooltip();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String m_Icon`  

```csharp
private System.String m_Icon;
```

- `private Game.UI.Tooltip.TooltipColor m_Color`  

```csharp
private Game.UI.Tooltip.TooltipColor m_Color;
```


## Properties

- `public System.String icon { get; set }`  

```csharp
public System.String icon { get; set; }
```

- `public Game.UI.Tooltip.TooltipColor color { get; set }`  

```csharp
public Game.UI.Tooltip.TooltipColor color { get; set; }
```


## Constructors

- `protected IconTooltip()`  

```csharp
protected IconTooltip();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("icon");
		writer.Write(icon);
		writer.PropertyName("color");
		writer.Write((int)color);
	}
```


