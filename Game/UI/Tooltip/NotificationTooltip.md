# Game.UI.Tooltip.NotificationTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class NotificationTooltip : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private System.String m_Name;
    private Game.UI.Tooltip.TooltipColor m_Color;
    private System.Boolean m_Verbose;

    public System.String name { get; set; }
    public Game.UI.Tooltip.TooltipColor color { get; set; }
    public System.Boolean verbose { get; set; }

    public NotificationTooltip();

    public static Game.UI.Tooltip.TooltipColor GetColor(Game.Notifications.IconPriority iconPriority);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String m_Name`  

```csharp
private System.String m_Name;
```

- `private Game.UI.Tooltip.TooltipColor m_Color`  

```csharp
private Game.UI.Tooltip.TooltipColor m_Color;
```

- `private System.Boolean m_Verbose`  

```csharp
private System.Boolean m_Verbose;
```


## Properties

- `public System.String name { get; set }`  

```csharp
public System.String name { get; set; }
```

- `public Game.UI.Tooltip.TooltipColor color { get; set }`  

```csharp
public Game.UI.Tooltip.TooltipColor color { get; set; }
```

- `public System.Boolean verbose { get; set }`  

```csharp
public System.Boolean verbose { get; set; }
```


## Constructors

- `public NotificationTooltip()`  

```csharp
public NotificationTooltip();
```


## Methods

- `public static GetColor(Game.Notifications.IconPriority iconPriority) : Game.UI.Tooltip.TooltipColor`  

```csharp
public static TooltipColor GetColor(IconPriority iconPriority)
	{
		if ((int)iconPriority >= 200)
		{
			return TooltipColor.Error;
		}
		if ((int)iconPriority >= 50)
		{
			return TooltipColor.Warning;
		}
		return TooltipColor.Info;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("name");
		writer.Write(name);
		writer.PropertyName("color");
		writer.Write((int)color);
		writer.PropertyName("verbose");
		writer.Write(verbose);
	}
```


