# Game.UI.Widgets.Float4SliderField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatSliderField<Unity.Mathematics.float4>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class Float4SliderField : Game.UI.Widgets.FloatSliderField<Unity.Mathematics.float4>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    protected Unity.Mathematics.float4 defaultMin { protected get; }
    protected Unity.Mathematics.float4 defaultMax { protected get; }

    public Float4SliderField();

    public virtual Unity.Mathematics.float4 ToFieldType(Unity.Mathematics.double4 value);
}
```


## Properties

- `protected Unity.Mathematics.float4 defaultMin { protected get }`  

```csharp
protected Unity.Mathematics.float4 defaultMin { protected get; }
```

- `protected Unity.Mathematics.float4 defaultMax { protected get }`  

```csharp
protected Unity.Mathematics.float4 defaultMax { protected get; }
```


## Constructors

- `public Float4SliderField()`  

```csharp
public Float4SliderField();
```


## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : Unity.Mathematics.float4`  

```csharp
public virtual Unity.Mathematics.float4 ToFieldType(Unity.Mathematics.double4 value);
```


