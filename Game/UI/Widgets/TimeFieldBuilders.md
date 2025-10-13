# Game.UI.Widgets.TimeFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class TimeFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public TimeFieldBuilders();

    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public TimeFieldBuilders()`  

```csharp
public TimeFieldBuilders();
```


## Methods

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(float))
		{
			if (WidgetAttributeUtils.IsTimeField(attributes))
			{
				float min = 0f;
				float max = 1f;
				WidgetAttributeUtils.GetNumberRange(attributes, ref min, ref max);
				return (IValueAccessor accessor) => new TimeSliderField
				{
					min = min,
					max = max,
					accessor = new CastAccessor<float>(accessor)
				};
			}
		}
		else if (memberType == typeof(Bounds1) && WidgetAttributeUtils.IsTimeField(attributes))
		{
			float min2 = 0f;
			float max2 = 1f;
			WidgetAttributeUtils.GetNumberRange(attributes, ref min2, ref max2);
			bool allowMinGreaterMax = WidgetAttributeUtils.AllowsMinGreaterMax(attributes);
			return (IValueAccessor accessor) => new TimeBoundsSliderField
			{
				min = min2,
				max = max2,
				allowMinGreaterMax = allowMinGreaterMax,
				accessor = new CastAccessor<Bounds1>(accessor)
			};
		}
		return null;
	}
```


## Nested types

- `Game.UI.Widgets.TimeFieldBuilders+<>c__DisplayClass0_0`  
- `Game.UI.Widgets.TimeFieldBuilders+<>c__DisplayClass0_1`  

