# Game.UI.Tooltip.ProgressTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.LabelIconTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class ProgressTooltip : Game.UI.Tooltip.LabelIconTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private System.Single m_Value;
    private System.Single m_Max;
    private System.String m_Unit;
    private System.Boolean m_OmitMax;
    public static const System.Single kCapacityWarningThreshold;

    public System.Single value { get; set; }
    public System.Single max { get; set; }
    public System.String unit { get; set; }
    public System.Boolean omitMax { get; set; }

    public ProgressTooltip();

    public static System.Void SetCapacityColor(Game.UI.Tooltip.ProgressTooltip tooltip);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Single m_Value`  

```csharp
private System.Single m_Value;
```

- `private System.Single m_Max`  

```csharp
private System.Single m_Max;
```

- `private System.String m_Unit`  

```csharp
private System.String m_Unit;
```

- `private System.Boolean m_OmitMax`  

```csharp
private System.Boolean m_OmitMax;
```

- `public static const System.Single kCapacityWarningThreshold`  

```csharp
public static const System.Single kCapacityWarningThreshold;
```


## Properties

- `public System.Single value { get; set }`  

```csharp
public System.Single value { get; set; }
```

- `public System.Single max { get; set }`  

```csharp
public System.Single max { get; set; }
```

- `public System.String unit { get; set }`  

```csharp
public System.String unit { get; set; }
```

- `public System.Boolean omitMax { get; set }`  

```csharp
public System.Boolean omitMax { get; set; }
```


## Constructors

- `public ProgressTooltip()`  

```csharp
public ProgressTooltip();
```


## Methods

- `public static SetCapacityColor(Game.UI.Tooltip.ProgressTooltip tooltip) : System.Void`  

```csharp
public static void SetCapacityColor(ProgressTooltip tooltip)
	{
		if (tooltip.value >= tooltip.max * 0.75f)
		{
			tooltip.color = TooltipColor.Info;
		}
		else if (tooltip.value > 0f)
		{
			tooltip.color = TooltipColor.Warning;
		}
		else
		{
			tooltip.color = TooltipColor.Error;
		}
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("value");
		writer.Write(value);
		writer.PropertyName("max");
		writer.Write(max);
		writer.PropertyName("unit");
		writer.Write(unit);
		writer.PropertyName("omitMax");
		writer.Write(omitMax);
	}
```


