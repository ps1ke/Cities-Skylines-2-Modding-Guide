# Game.UI.Widgets.EulerAnglesField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatField<Unity.Mathematics.float3>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class EulerAnglesField : Game.UI.Widgets.FloatField<Unity.Mathematics.float3>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    protected Unity.Mathematics.float3 defaultMin { protected get; }
    protected Unity.Mathematics.float3 defaultMax { protected get; }

    public EulerAnglesField();

    public virtual Unity.Mathematics.float3 ToFieldType(Unity.Mathematics.double4 value);
}
```


## Properties

- `protected Unity.Mathematics.float3 defaultMin { protected get }`  

```csharp
protected Unity.Mathematics.float3 defaultMin { protected get; }
```

- `protected Unity.Mathematics.float3 defaultMax { protected get }`  

```csharp
protected Unity.Mathematics.float3 defaultMax { protected get; }
```


## Constructors

- `public EulerAnglesField()`  

```csharp
public EulerAnglesField();
```


## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : Unity.Mathematics.float3`  

```csharp
public override float3 ToFieldType(double4 value)
	{
		return new float3(value.xyz);
	}
```


