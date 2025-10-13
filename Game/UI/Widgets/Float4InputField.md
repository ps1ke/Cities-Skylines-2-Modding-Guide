# Game.UI.Widgets.Float4InputField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatField<Unity.Mathematics.float4>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class Float4InputField : Game.UI.Widgets.FloatField<Unity.Mathematics.float4>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    protected Unity.Mathematics.float4 defaultMin { protected get; }
    protected Unity.Mathematics.float4 defaultMax { protected get; }

    public Float4InputField();

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

- `public Float4InputField()`  

```csharp
public Float4InputField();
```


## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : Unity.Mathematics.float4`  

```csharp
public override float4 ToFieldType(double4 value)
	{
		return new float4(value);
	}
```


