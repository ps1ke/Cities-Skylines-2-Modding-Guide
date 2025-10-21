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
protected virtual Game.UI.Widgets.WidgetChanges Update();
```


## Nested types

- `Game.UI.Widgets.AnimationCurveField+Bindings`  

