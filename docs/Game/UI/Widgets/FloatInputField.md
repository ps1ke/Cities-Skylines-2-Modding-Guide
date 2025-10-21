# Game.UI.Widgets.FloatInputField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatField<System.Double>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class FloatInputField : Game.UI.Widgets.FloatField<System.Double>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    protected System.Double defaultMin { protected get; }
    protected System.Double defaultMax { protected get; }

    public FloatInputField();

    public virtual System.Double ToFieldType(Unity.Mathematics.double4 value);
}
```


## Properties

- `protected System.Double defaultMin { protected get }`  

```csharp
protected System.Double defaultMin { protected get; }
```

- `protected System.Double defaultMax { protected get }`  

```csharp
protected System.Double defaultMax { protected get; }
```


## Constructors

- `public FloatInputField()`  

```csharp
public FloatInputField();
```


## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : System.Double`  

```csharp
public virtual System.Double ToFieldType(Unity.Mathematics.double4 value);
```


