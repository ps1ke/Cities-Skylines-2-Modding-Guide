# Game.UI.Widgets.FloatSliderField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatSliderField<System.Double>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Code

```csharp
public class FloatSliderField : Game.UI.Widgets.FloatSliderField<System.Double>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IWarning
{
    private System.Boolean m_Warning;
    private System.Func<System.Boolean> <warningAction>k__BackingField;

    public System.Func<System.Boolean> warningAction { get; set; }
    protected System.Double defaultMin { protected get; }
    protected System.Double defaultMax { protected get; }
    public System.Boolean warning { get; set; }

    public FloatSliderField();

    public virtual System.Double ToFieldType(Unity.Mathematics.double4 value);
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


## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  

```csharp
public System.Func<System.Boolean> warningAction { get; set; }
```

- `protected System.Double defaultMin { protected get }`  

```csharp
protected System.Double defaultMin { protected get; }
```

- `protected System.Double defaultMax { protected get }`  

```csharp
protected System.Double defaultMax { protected get; }
```

- `public System.Boolean warning { get; set }`  

```csharp
public System.Boolean warning { get; set; }
```


## Constructors

- `public FloatSliderField()`  

```csharp
public FloatSliderField();
```


## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : System.Double`  

```csharp
public override double ToFieldType(double4 value)
	{
		return value.x;
	}
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		if (warningAction != null)
		{
			bool flag = warningAction();
			if (flag != m_Warning)
			{
				m_Warning = flag;
				widgetChanges |= WidgetChanges.Properties;
			}
		}
		return widgetChanges;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("warning");
		writer.Write(warning);
	}
```


