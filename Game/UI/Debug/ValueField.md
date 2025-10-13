# Game.UI.Debug.ValueField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Debug`  

**Type:** class public  

**Base:** `Game.UI.Widgets.ValueField`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`  

## Code

```csharp
public class ValueField : Game.UI.Widgets.ValueField, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider
{
    private UnityEngine.Rendering.DebugUI+Value m_DebugWidget;
    private System.Object m_ObjectValue;
    private System.String m_StringValue;
    private System.Single m_Timer;

    public System.String propertiesTypeName { get; }

    public ValueField(UnityEngine.Rendering.DebugUI+Value debugWidget);

    public virtual System.String GetValue();
    protected virtual Game.UI.Widgets.WidgetChanges Update();
}
```


## Fields

- `private UnityEngine.Rendering.DebugUI+Value m_DebugWidget`  

```csharp
private UnityEngine.Rendering.DebugUI+Value m_DebugWidget;
```

- `private System.Object m_ObjectValue`  

```csharp
private System.Object m_ObjectValue;
```

- `private System.String m_StringValue`  

```csharp
private System.String m_StringValue;
```

- `private System.Single m_Timer`  

```csharp
private System.Single m_Timer;
```


## Properties

- `public System.String propertiesTypeName { get }`  

```csharp
public System.String propertiesTypeName { get; }
```


## Constructors

- `public ValueField(UnityEngine.Rendering.DebugUI+Value debugWidget)`  

```csharp
public ValueField(DebugUI.Value debugWidget)
	{
		m_DebugWidget = debugWidget;
	}
```


## Methods

- `public virtual GetValue() : System.String`  

```csharp
public override string GetValue()
	{
		return m_StringValue ?? string.Empty;
	}
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		m_Timer -= Time.deltaTime;
		if (m_Timer <= 0f)
		{
			m_Timer = m_DebugWidget.refreshRate;
			object value = m_DebugWidget.GetValue();
			if (!object.Equals(value, m_ObjectValue))
			{
				m_ObjectValue = value;
				m_StringValue = m_DebugWidget.FormatString(m_ObjectValue);
			}
		}
		return base.Update();
	}
```


