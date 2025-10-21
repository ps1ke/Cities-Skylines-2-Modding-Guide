# Game.UI.Debug.IntInputField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Debug`  

**Type:** class public  

**Base:** `Game.UI.Widgets.IntInputField`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class IntInputField : Game.UI.Widgets.IntInputField, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    private Game.Debug.IntInputField m_DebugWidget;
    private System.String m_StringValue;
    private System.Int32 m_IntValue;

    public System.String propertiesTypeName { get; }

    public IntInputField(Game.Debug.IntInputField debugWidget);

    public virtual System.Int32 GetValue();
    public virtual System.Void SetValue(System.Int32 value);
    protected virtual Game.UI.Widgets.WidgetChanges Update();
}
```


## Fields

- `private Game.Debug.IntInputField m_DebugWidget`  

```csharp
private Game.Debug.IntInputField m_DebugWidget;
```

- `private System.String m_StringValue`  

```csharp
private System.String m_StringValue;
```

- `private System.Int32 m_IntValue`  

```csharp
private System.Int32 m_IntValue;
```


## Properties

- `public System.String propertiesTypeName { get }`  

```csharp
public System.String propertiesTypeName { get; }
```


## Constructors

- `public IntInputField(Game.Debug.IntInputField debugWidget)`  

```csharp
public IntInputField(Game.Debug.IntInputField debugWidget);
```


## Methods

- `public virtual GetValue() : System.Int32`  

```csharp
public virtual System.Int32 GetValue();
```

- `public virtual SetValue(System.Int32 value) : System.Void`  

```csharp
public virtual System.Void SetValue(System.Int32 value);
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```


