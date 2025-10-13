# Game.UI.Widgets.IconButton

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IInvokable`  

## Code

```csharp
public class IconButton : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IInvokable
{
    private System.Boolean m_Selected;
    private System.String m_Icon;
    private System.Action <action>k__BackingField;
    private System.Func<System.Boolean> <selected>k__BackingField;
    private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField;

    public System.String icon { get; set; }
    public System.Action action { get; set; }
    public System.Func<System.Boolean> selected { get; set; }
    public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set; }

    public IconButton();

    public System.Void Invoke();
    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean m_Selected`  

```csharp
private System.Boolean m_Selected;
```

- `private System.String m_Icon`  

```csharp
private System.String m_Icon;
```

- `private System.Action <action>k__BackingField`  

```csharp
private System.Action <action>k__BackingField;
```

- `private System.Func<System.Boolean> <selected>k__BackingField`  

```csharp
private System.Func<System.Boolean> <selected>k__BackingField;
```

- `private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField`  

```csharp
private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField;
```


## Properties

- `public System.String icon { get; set }`  

```csharp
public System.String icon { get; set; }
```

- `public System.Action action { get; set }`  

```csharp
public System.Action action { get; set; }
```

- `public System.Func<System.Boolean> selected { get; set }`  

```csharp
public System.Func<System.Boolean> selected { get; set; }
```

- `public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set }`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set; }
```


## Constructors

- `public IconButton()`  

```csharp
public IconButton();
```


## Methods

- `public Invoke() : System.Void`  

```csharp
public void Invoke()
	{
		action();
	}
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		bool flag = selected != null && selected();
		if (flag != m_Selected)
		{
			widgetChanges |= WidgetChanges.Properties;
			m_Selected = flag;
		}
		return widgetChanges;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("icon");
		writer.Write(icon);
		writer.PropertyName("selected");
		writer.Write(m_Selected);
		writer.PropertyName("tooltip");
		writer.Write(tooltip);
	}
```


