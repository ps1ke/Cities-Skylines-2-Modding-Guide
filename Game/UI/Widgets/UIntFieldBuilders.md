# Game.UI.Widgets.UIntFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class UIntFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    private static readonly System.UInt32 kGlobalValueRange;

    public UIntFieldBuilders();

    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Fields

- `private static readonly System.UInt32 kGlobalValueRange`  

```csharp
private static readonly System.UInt32 kGlobalValueRange;
```


## Constructors

- `public UIntFieldBuilders()`  

```csharp
public UIntFieldBuilders();
```


## Methods

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(uint))
		{
			uint min = 0u;
			uint max = ((!EditorGenerator.sBypassValueLimits) ? kGlobalValueRange : uint.MaxValue);
			uint step = WidgetAttributeUtils.GetNumberStep(attributes, 1u);
			if (WidgetAttributeUtils.GetNumberRange(attributes, ref min, ref max) && !WidgetAttributeUtils.RequiresInputField(attributes))
			{
				string unit = WidgetAttributeUtils.GetNumberUnit(attributes);
				return (IValueAccessor accessor) => new UIntSliderField
				{
					min = min,
					max = max,
					step = step,
					unit = unit,
					accessor = new CastAccessor<uint>(accessor)
				};
			}
			return (IValueAccessor accessor) => new UIntInputField
			{
				min = min,
				max = max,
				step = step,
				accessor = new CastAccessor<uint>(accessor)
			};
		}
		return null;
	}
```


## Nested types

- `Game.UI.Widgets.UIntFieldBuilders+<>c__DisplayClass1_0`  
- `Game.UI.Widgets.UIntFieldBuilders+<>c__DisplayClass1_1`  

