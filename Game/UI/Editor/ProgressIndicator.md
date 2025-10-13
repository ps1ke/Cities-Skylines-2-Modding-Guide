# Game.UI.Editor.ProgressIndicator

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidgetWithTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`  

## Code

```csharp
public class ProgressIndicator : Game.UI.Widgets.NamedWidgetWithTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider
{
    private System.Single m_Progress;
    private Game.UI.Editor.ProgressIndicator+State m_State;
    private System.Func<System.Single> <progress>k__BackingField;
    private System.Func<Game.UI.Editor.ProgressIndicator+State> <state>k__BackingField;

    public System.Func<System.Single> progress { get; set; }
    public System.Func<Game.UI.Editor.ProgressIndicator+State> state { get; set; }

    public ProgressIndicator();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Single m_Progress`  

```csharp
private System.Single m_Progress;
```

- `private Game.UI.Editor.ProgressIndicator+State m_State`  

```csharp
private Game.UI.Editor.ProgressIndicator+State m_State;
```

- `private System.Func<System.Single> <progress>k__BackingField`  

```csharp
private System.Func<System.Single> <progress>k__BackingField;
```

- `private System.Func<Game.UI.Editor.ProgressIndicator+State> <state>k__BackingField`  

```csharp
private System.Func<Game.UI.Editor.ProgressIndicator+State> <state>k__BackingField;
```


## Properties

- `public System.Func<System.Single> progress { get; set }`  

```csharp
public System.Func<System.Single> progress { get; set; }
```

- `public System.Func<Game.UI.Editor.ProgressIndicator+State> state { get; set }`  

```csharp
public System.Func<Game.UI.Editor.ProgressIndicator+State> state { get; set; }
```


## Constructors

- `public ProgressIndicator()`  

```csharp
public ProgressIndicator();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		if (this.state != null)
		{
			State state = this.state();
			if (state != m_State)
			{
				m_State = state;
				widgetChanges |= WidgetChanges.Properties;
			}
		}
		if (progress != null)
		{
			float a = progress();
			if (!Mathf.Approximately(a, m_Progress))
			{
				m_Progress = a;
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
		writer.PropertyName("state");
		writer.Write((int)m_State);
		writer.PropertyName("progress");
		writer.Write(m_Progress);
		writer.PropertyName("indeterminate");
		writer.Write(progress == null);
	}
```


## Nested types

- `Game.UI.Editor.ProgressIndicator+State`  

