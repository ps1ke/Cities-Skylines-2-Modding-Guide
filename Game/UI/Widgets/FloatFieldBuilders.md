# Game.UI.Widgets.FloatFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class FloatFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    private static const System.Double kGlobalValueRange;

    public FloatFieldBuilders();

    internal static System.Object <TryCreate>g__FromDouble|1_3(System.Double value);
    internal static System.Object <TryCreate>g__FromEulerAngles|1_11(Unity.Mathematics.float3 value);
    internal static System.Object <TryCreate>g__FromEulerAngles|1_9(Unity.Mathematics.float3 value);
    internal static System.Object <TryCreate>g__FromFloat|1_1(System.Double value);
    internal static System.Object <TryCreate>g__FromVector2|1_5(Unity.Mathematics.float2 value);
    internal static System.Object <TryCreate>g__FromVector3|1_7(Unity.Mathematics.float3 value);
    internal static System.Object <TryCreate>g__FromVector4|1_13(Unity.Mathematics.float4 value);
    internal static System.Double <TryCreate>g__ToDouble|1_2(System.Object value);
    internal static Unity.Mathematics.float3 <TryCreate>g__ToEulerAngles|1_10(System.Object value);
    internal static Unity.Mathematics.float3 <TryCreate>g__ToEulerAngles|1_8(System.Object value);
    internal static System.Double <TryCreate>g__ToFloat|1_0(System.Object value);
    internal static Unity.Mathematics.float2 <TryCreate>g__ToVector2|1_4(System.Object value);
    internal static Unity.Mathematics.float3 <TryCreate>g__ToVector3|1_6(System.Object value);
    internal static Unity.Mathematics.float4 <TryCreate>g__ToVector4|1_12(System.Object value);
    private static Game.UI.Widgets.FieldBuilder CreateFloatFieldBuilder(System.Object[] attributes, System.Double min, System.Double max, System.Converter<System.Object, System.Double> fromObject, System.Converter<System.Double, System.Object> toObject);
    private static Game.UI.Widgets.FieldBuilder CreateFloatFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject, System.Converter<TValue, System.Object> toObject);
    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Fields

- `private static const System.Double kGlobalValueRange`  

```csharp
private static const System.Double kGlobalValueRange;
```


## Constructors

- `public FloatFieldBuilders()`  

```csharp
public FloatFieldBuilders();
```


## Methods

- `internal static <TryCreate>g__FromDouble|1_3(System.Double value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromDouble|1_3(System.Double value);
```

- `internal static <TryCreate>g__FromEulerAngles|1_11(Unity.Mathematics.float3 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromEulerAngles|1_11(Unity.Mathematics.float3 value);
```

- `internal static <TryCreate>g__FromEulerAngles|1_9(Unity.Mathematics.float3 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromEulerAngles|1_9(Unity.Mathematics.float3 value);
```

- `internal static <TryCreate>g__FromFloat|1_1(System.Double value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromFloat|1_1(System.Double value);
```

- `internal static <TryCreate>g__FromVector2|1_5(Unity.Mathematics.float2 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromVector2|1_5(Unity.Mathematics.float2 value);
```

- `internal static <TryCreate>g__FromVector3|1_7(Unity.Mathematics.float3 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromVector3|1_7(Unity.Mathematics.float3 value);
```

- `internal static <TryCreate>g__FromVector4|1_13(Unity.Mathematics.float4 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromVector4|1_13(Unity.Mathematics.float4 value);
```

- `internal static <TryCreate>g__ToDouble|1_2(System.Object value) : System.Double`  

```csharp
internal static System.Double <TryCreate>g__ToDouble|1_2(System.Object value);
```

- `internal static <TryCreate>g__ToEulerAngles|1_10(System.Object value) : Unity.Mathematics.float3`  

```csharp
internal static Unity.Mathematics.float3 <TryCreate>g__ToEulerAngles|1_10(System.Object value);
```

- `internal static <TryCreate>g__ToEulerAngles|1_8(System.Object value) : Unity.Mathematics.float3`  

```csharp
internal static Unity.Mathematics.float3 <TryCreate>g__ToEulerAngles|1_8(System.Object value);
```

- `internal static <TryCreate>g__ToFloat|1_0(System.Object value) : System.Double`  

```csharp
internal static System.Double <TryCreate>g__ToFloat|1_0(System.Object value);
```

- `internal static <TryCreate>g__ToVector2|1_4(System.Object value) : Unity.Mathematics.float2`  

```csharp
internal static Unity.Mathematics.float2 <TryCreate>g__ToVector2|1_4(System.Object value);
```

- `internal static <TryCreate>g__ToVector3|1_6(System.Object value) : Unity.Mathematics.float3`  

```csharp
internal static Unity.Mathematics.float3 <TryCreate>g__ToVector3|1_6(System.Object value);
```

- `internal static <TryCreate>g__ToVector4|1_12(System.Object value) : Unity.Mathematics.float4`  

```csharp
internal static Unity.Mathematics.float4 <TryCreate>g__ToVector4|1_12(System.Object value);
```

- `private static CreateFloatFieldBuilder(System.Object[] attributes, System.Double min, System.Double max, System.Converter<System.Object, System.Double> fromObject, System.Converter<System.Double, System.Object> toObject) : Game.UI.Widgets.FieldBuilder`  

```csharp
private static FieldBuilder CreateFloatFieldBuilder(object[] attributes, double min, double max, Converter<object, double> fromObject, Converter<double, object> toObject)
	{
		if (!EditorGenerator.sBypassValueLimits)
		{
			min = math.max(min, -10000000.0);
			max = math.min(max, 10000000.0);
		}
		double step = WidgetAttributeUtils.GetNumberStep(attributes, 0.01);
		if (!EditorGenerator.sBypassValueLimits && WidgetAttributeUtils.GetNumberRange(attributes, ref min, ref max) && !WidgetAttributeUtils.RequiresInputField(attributes))
		{
			string unit = WidgetAttributeUtils.GetNumberUnit(attributes);
			return (IValueAccessor accessor) => new FloatSliderField
			{
				min = min,
				max = max,
				step = step,
				unit = unit,
				accessor = new CastAccessor<double>(accessor, fromObject, toObject)
			};
		}
		return (IValueAccessor accessor) => new FloatInputField
		{
			min = min,
			max = max,
			step = step,
			accessor = new CastAccessor<double>(accessor, fromObject, toObject)
		};
	}
```

- `private static CreateFloatFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject = null, System.Converter<TValue, System.Object> toObject = null) : Game.UI.Widgets.FieldBuilder`  

```csharp
private static Game.UI.Widgets.FieldBuilder CreateFloatFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject, System.Converter<TValue, System.Object> toObject);
```

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(float))
		{
			return CreateFloatFieldBuilder(attributes, -3.4028234663852886E+38, 3.4028234663852886E+38, ToFloat, FromFloat);
		}
		if (memberType == typeof(double))
		{
			return CreateFloatFieldBuilder(attributes, double.MinValue, double.MaxValue, ToDouble, FromDouble);
		}
		if (memberType == typeof(float2))
		{
			return CreateFloatFieldBuilder<Float2InputField, float2>(attributes);
		}
		if (memberType == typeof(Vector2))
		{
			return CreateFloatFieldBuilder<Float2InputField, float2>(attributes, ToVector, FromVector);
		}
		if (memberType == typeof(float3))
		{
			return CreateFloatFieldBuilder<Float3InputField, float3>(attributes);
		}
		if (memberType == typeof(Vector3))
		{
			return CreateFloatFieldBuilder<Float3InputField, float3>(attributes, ToVector3, FromVector3);
		}
		if (memberType == typeof(quaternion))
		{
			return CreateFloatFieldBuilder<EulerAnglesField, float3>(attributes, ToEulerAngles, FromEulerAngles);
		}
		if (memberType == typeof(Quaternion))
		{
			return CreateFloatFieldBuilder<EulerAnglesField, float3>(attributes, ToEulerAngles2, FromEulerAngles2);
		}
		if (memberType == typeof(float4))
		{
			return CreateFloatFieldBuilder<Float4InputField, float4>(attributes);
		}
		if (memberType == typeof(Vector4))
		{
			return CreateFloatFieldBuilder<Float4InputField, float4>(attributes, ToVector4, FromVector4);
		}
		return null;
		static object FromDouble(double value)
		{
			return value;
		}
		static object FromEulerAngles(float3 value)
		{
			return (quaternion)Quaternion.Euler(value);
		}
		static object FromEulerAngles2(float3 value)
		{
			return Quaternion.Euler(value);
		}
		static object FromFloat(double value)
		{
			return (float)value;
		}
		static object FromVector(float2 value)
		{
			return (Vector2)value;
		}
		static object FromVector3(float3 value)
		{
			return (Vector3)value;
		}
		static object FromVector4(float4 value)
		{
			return (Vector4)value;
		}
		static double ToDouble(object value)
		{
			return (double)value;
		}
		static float3 ToEulerAngles(object value)
		{
			return ((Quaternion)(quaternion)value).eulerAngles;
		}
		static float3 ToEulerAngles2(object value)
		{
			return ((Quaternion)value).eulerAngles;
		}
		static double ToFloat(object value)
		{
			return (float)value;
		}
		static float2 ToVector(object value)
		{
			return (Vector2)value;
		}
		static float3 ToVector3(object value)
		{
			return (Vector3)value;
		}
		static float4 ToVector4(object value)
		{
			return (Vector4)value;
		}
	}
```


## Nested types

- `Game.UI.Widgets.FloatFieldBuilders+<>c__DisplayClass2_0`  
- `Game.UI.Widgets.FloatFieldBuilders+<>c__DisplayClass2_1`  
- `Game.UI.Widgets.FloatFieldBuilders+<>c__DisplayClass3_0<TWidget, TValue>`  

