# Game.UI.Editor.TimeOfDayWeightsFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class TimeOfDayWeightsFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public TimeOfDayWeightsFieldBuilders();

    internal static System.Object <TryCreate>g__FromFloat|0_1(System.Double value);
    internal static System.Double <TryCreate>g__ToFloat|0_0(System.Object value);
    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public TimeOfDayWeightsFieldBuilders()`  

```csharp
public TimeOfDayWeightsFieldBuilders();
```


## Methods

- `internal static <TryCreate>g__FromFloat|0_1(System.Double value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromFloat|0_1(System.Double value);
```

- `internal static <TryCreate>g__ToFloat|0_0(System.Object value) : System.Double`  

```csharp
internal static System.Double <TryCreate>g__ToFloat|0_0(System.Object value);
```

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(float4))
		{
			float min = 0f;
			float max = 1f;
			WidgetAttributeUtils.GetNumberRange(attributes, ref min, ref max);
			float step = WidgetAttributeUtils.GetNumberStep(attributes, 0.1f);
			FieldInfo xField = typeof(float4).GetField("x");
			FieldInfo yField = typeof(float4).GetField("y");
			FieldInfo zField = typeof(float4).GetField("z");
			FieldInfo wField = typeof(float4).GetField("w");
			return (IValueAccessor accessor) => new Group
			{
				children = new IWidget[5]
				{
					new FloatSliderField
					{
						path = "x",
						displayName = "Night",
						min = min,
						max = max,
						fractionDigits = 1,
						step = step,
						accessor = new CastAccessor<double>(new FieldAccessor(accessor, xField), ToFloat, FromFloat)
					},
					new FloatSliderField
					{
						path = "y",
						displayName = "Morning",
						min = min,
						max = max,
						fractionDigits = 1,
						step = step,
						accessor = new CastAccessor<double>(new FieldAccessor(accessor, yField), ToFloat, FromFloat)
					},
					new FloatSliderField
					{
						path = "z",
						displayName = "Day",
						min = min,
						max = max,
						fractionDigits = 1,
						step = step,
						accessor = new CastAccessor<double>(new FieldAccessor(accessor, zField), ToFloat, FromFloat)
					},
					new FloatSliderField
					{
						path = "w",
						displayName = "Evening",
						min = min,
						max = max,
						fractionDigits = 1,
						step = step,
						accessor = new CastAccessor<double>(new FieldAccessor(accessor, wField), ToFloat, FromFloat)
					},
					new TimeOfDayWeightsChart
					{
						min = min,
						max = max,
						accessor = new CastAccessor<float4>(accessor)
					}
				}
			};
		}
		return null;
		static object FromFloat(double value)
		{
			return (float)value;
		}
		static double ToFloat(object value)
		{
			return (float)value;
		}
	}
```


## Nested types

- `Game.UI.Editor.TimeOfDayWeightsFieldBuilders+<>c__DisplayClass0_0`  

