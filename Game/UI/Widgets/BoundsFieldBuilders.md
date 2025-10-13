# Game.UI.Widgets.BoundsFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class BoundsFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public BoundsFieldBuilders();

    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public BoundsFieldBuilders()`  

```csharp
public BoundsFieldBuilders();
```


## Methods

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(Bounds1))
		{
			float min = float.MinValue;
			float max = float.MaxValue;
			float step = WidgetAttributeUtils.GetNumberStep(attributes, 0.01f);
			bool allowMinGreaterMax = WidgetAttributeUtils.AllowsMinGreaterMax(attributes);
			if (WidgetAttributeUtils.GetNumberRange(attributes, ref min, ref max) && !WidgetAttributeUtils.RequiresInputField(attributes))
			{
				return (IValueAccessor accessor) => new Bounds1SliderField
				{
					min = min,
					max = max,
					step = step,
					allowMinGreaterMax = allowMinGreaterMax,
					accessor = new CastAccessor<Bounds1>(accessor)
				};
			}
			return (IValueAccessor accessor) => new Bounds1InputField
			{
				min = min,
				max = max,
				step = step,
				allowMinGreaterMax = allowMinGreaterMax,
				accessor = new CastAccessor<Bounds1>(accessor)
			};
		}
		if (memberType == typeof(Bounds2))
		{
			bool allowMinGreaterMax2 = WidgetAttributeUtils.AllowsMinGreaterMax(attributes);
			return (IValueAccessor accessor) => new Bounds2InputField
			{
				allowMinGreaterMax = allowMinGreaterMax2,
				accessor = new CastAccessor<Bounds2>(accessor)
			};
		}
		if (memberType == typeof(Bounds3))
		{
			bool allowMinGreaterMax3 = WidgetAttributeUtils.AllowsMinGreaterMax(attributes);
			return (IValueAccessor accessor) => new Bounds3InputField
			{
				allowMinGreaterMax = allowMinGreaterMax3,
				accessor = new CastAccessor<Bounds3>(accessor)
			};
		}
		return null;
	}
```


## Nested types

- `Game.UI.Widgets.BoundsFieldBuilders+<>c__DisplayClass0_0`  
- `Game.UI.Widgets.BoundsFieldBuilders+<>c__DisplayClass0_1`  
- `Game.UI.Widgets.BoundsFieldBuilders+<>c__DisplayClass0_2`  

