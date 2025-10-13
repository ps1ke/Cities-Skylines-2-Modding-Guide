# Game.UI.Widgets.AnimationCurveField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<UnityEngine.AnimationCurve>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IMutable<UnityEngine.AnimationCurve>`  

## Code

```csharp
public class AnimationCurveField : Game.UI.Widgets.Field<UnityEngine.AnimationCurve>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IMutable<UnityEngine.AnimationCurve>
{
    private System.Collections.Generic.List<UnityEngine.Keyframe> m_Keys;
    private UnityEngine.WrapMode m_PreWrapMode;
    private UnityEngine.WrapMode m_PostWrapMode;

    public AnimationCurveField();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
}
```


## Fields

- `private System.Collections.Generic.List<UnityEngine.Keyframe> m_Keys`  

```csharp
private System.Collections.Generic.List<UnityEngine.Keyframe> m_Keys;
```

- `private UnityEngine.WrapMode m_PreWrapMode`  

```csharp
private UnityEngine.WrapMode m_PreWrapMode;
```

- `private UnityEngine.WrapMode m_PostWrapMode`  

```csharp
private UnityEngine.WrapMode m_PostWrapMode;
```


## Constructors

- `public AnimationCurveField()`  

```csharp
public AnimationCurveField();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		Keyframe[] keys = m_Value.keys;
		if (!m_Keys.SequenceEqual(keys))
		{
			widgetChanges |= WidgetChanges.Properties;
			m_Keys.Clear();
			m_Keys.AddRange(keys);
		}
		if (m_Value.preWrapMode != m_PreWrapMode)
		{
			widgetChanges |= WidgetChanges.Properties;
			m_PreWrapMode = m_Value.preWrapMode;
		}
		if (m_Value.postWrapMode != m_PostWrapMode)
		{
			widgetChanges |= WidgetChanges.Properties;
			m_PostWrapMode = m_Value.postWrapMode;
		}
		return widgetChanges;
	}
```


## Nested types

- `Game.UI.Widgets.AnimationCurveField+Bindings`  

