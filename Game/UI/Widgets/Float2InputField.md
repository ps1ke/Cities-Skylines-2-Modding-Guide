# Game.UI.Widgets.Float2InputField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatField<Unity.Mathematics.float2>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class Float2InputField : Game.UI.Widgets.FloatField<Unity.Mathematics.float2>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    protected Unity.Mathematics.float2 defaultMin { protected get; }
    protected Unity.Mathematics.float2 defaultMax { protected get; }

    public Float2InputField();

    public virtual Unity.Mathematics.float2 ToFieldType(Unity.Mathematics.double4 value);
}
```


## Properties

- `protected Unity.Mathematics.float2 defaultMin { protected get }`  

```csharp
protected Unity.Mathematics.float2 defaultMin { protected get; }
```

- `protected Unity.Mathematics.float2 defaultMax { protected get }`  

```csharp
protected Unity.Mathematics.float2 defaultMax { protected get; }
```


## Constructors

- `public Float2InputField()`  

```csharp
public Float2InputField();
```


## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : Unity.Mathematics.float2`  

```csharp
public override float2 ToFieldType(double4 value)
	{
		return new float2(value.xy);
	}
```


