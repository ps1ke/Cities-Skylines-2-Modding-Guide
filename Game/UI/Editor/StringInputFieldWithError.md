# Game.UI.Editor.StringInputFieldWithError

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.StringInputField`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Code

```csharp
public class StringInputFieldWithError : Game.UI.Widgets.StringInputField, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IWarning
{
    private System.Boolean m_Error;
    private System.Func<System.Boolean> <error>k__BackingField;
    private Game.UI.Localization.LocalizedString <errorMessage>k__BackingField;

    public System.Func<System.Boolean> error { get; set; }
    public Game.UI.Localization.LocalizedString errorMessage { get; set; }

    public StringInputFieldWithError();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean m_Error`  

```csharp
private System.Boolean m_Error;
```

- `private System.Func<System.Boolean> <error>k__BackingField`  

```csharp
private System.Func<System.Boolean> <error>k__BackingField;
```

- `private Game.UI.Localization.LocalizedString <errorMessage>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <errorMessage>k__BackingField;
```


## Properties

- `public System.Func<System.Boolean> error { get; set }`  

```csharp
public System.Func<System.Boolean> error { get; set; }
```

- `public Game.UI.Localization.LocalizedString errorMessage { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString errorMessage { get; set; }
```


## Constructors

- `public StringInputFieldWithError()`  

```csharp
public StringInputFieldWithError();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		if (error != null)
		{
			bool flag = error();
			if (m_Error != flag)
			{
				widgetChanges |= WidgetChanges.Properties;
			}
			m_Error = flag;
		}
		return widgetChanges;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("error");
		writer.Write(m_Error);
		writer.PropertyName("errorMessage");
		writer.Write(errorMessage);
	}
```


