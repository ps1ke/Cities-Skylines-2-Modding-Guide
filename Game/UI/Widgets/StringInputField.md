# Game.UI.Widgets.StringInputField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<System.String>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Code

```csharp
public class StringInputField : Game.UI.Widgets.Field<System.String>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IWarning
{
    private System.Boolean m_Warning;
    private System.Func<System.Boolean> <warningAction>k__BackingField;
    private System.Int32 m_Multiline;
    private System.Int32 m_MaxLength;
    public static readonly System.Int32 kDefaultMultilines;
    public static readonly System.Int32 kSingleLine;

    public System.Func<System.Boolean> warningAction { get; set; }
    public System.Int32 multiline { get; set; }
    public System.Int32 maxLength { get; set; }
    public System.Boolean warning { get; set; }

    public StringInputField();

    public virtual System.String GetValue();
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

- `private System.Int32 m_Multiline`  

```csharp
private System.Int32 m_Multiline;
```

- `private System.Int32 m_MaxLength`  

```csharp
private System.Int32 m_MaxLength;
```

- `public static readonly System.Int32 kDefaultMultilines`  

```csharp
public static readonly System.Int32 kDefaultMultilines;
```

- `public static readonly System.Int32 kSingleLine`  

```csharp
public static readonly System.Int32 kSingleLine;
```


## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  

```csharp
public System.Func<System.Boolean> warningAction { get; set; }
```

- `public System.Int32 multiline { get; set }`  

```csharp
public System.Int32 multiline { get; set; }
```

- `public System.Int32 maxLength { get; set }`  

```csharp
public System.Int32 maxLength { get; set; }
```

- `public System.Boolean warning { get; set }`  

```csharp
public System.Boolean warning { get; set; }
```


## Constructors

- `public StringInputField()`  

```csharp
public StringInputField();
```


## Methods

- `public virtual GetValue() : System.String`  

```csharp
public override string GetValue()
	{
		return base.GetValue() ?? string.Empty;
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
		writer.PropertyName("multiline");
		writer.Write(m_Multiline);
		writer.PropertyName("maxLength");
		writer.Write(m_MaxLength);
		writer.PropertyName("warning");
		writer.Write(warning);
	}
```


