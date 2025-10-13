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
public ValueField(UnityEngine.Rendering.DebugUI+Value debugWidget);
```


## Methods

- `public virtual GetValue() : System.String`  

```csharp
public virtual System.String GetValue();
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```


