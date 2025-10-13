# Game.UI.Widgets.IntFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class IntFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    private static readonly System.Int32 kGlobalValueRange;

    public IntFieldBuilders();

    internal static System.Object <TryCreate>g__FromByte|1_1(System.Int32 value);
    internal static System.Object <TryCreate>g__FromInt|1_9(System.Int32 value);
    internal static System.Object <TryCreate>g__FromInt2|1_11(Unity.Mathematics.int2 value);
    internal static System.Object <TryCreate>g__FromInt3|1_15(Unity.Mathematics.int3 value);
    internal static System.Object <TryCreate>g__FromInt4|1_19(Unity.Mathematics.int4 value);
    internal static System.Object <TryCreate>g__FromSByte|1_3(System.Int32 value);
    internal static System.Object <TryCreate>g__FromShort|1_5(System.Int32 value);
    internal static System.Object <TryCreate>g__FromUShort|1_7(System.Int32 value);
    internal static System.Object <TryCreate>g__FromVector2Int|1_13(Unity.Mathematics.int2 value);
    internal static System.Object <TryCreate>g__FromVector3Int|1_17(Unity.Mathematics.int3 value);
    internal static System.Int32 <TryCreate>g__ToByte|1_0(System.Object value);
    internal static System.Int32 <TryCreate>g__ToInt|1_8(System.Object value);
    internal static Unity.Mathematics.int2 <TryCreate>g__ToInt2|1_10(System.Object value);
    internal static Unity.Mathematics.int3 <TryCreate>g__ToInt3|1_14(System.Object value);
    internal static Unity.Mathematics.int4 <TryCreate>g__ToInt4|1_18(System.Object value);
    internal static System.Int32 <TryCreate>g__ToSByte|1_2(System.Object value);
    internal static System.Int32 <TryCreate>g__ToShort|1_4(System.Object value);
    internal static System.Int32 <TryCreate>g__ToUShort|1_6(System.Object value);
    internal static Unity.Mathematics.int2 <TryCreate>g__ToVector2Int|1_12(System.Object value);
    internal static Unity.Mathematics.int3 <TryCreate>g__ToVector3Int|1_16(System.Object value);
    private static Game.UI.Widgets.FieldBuilder CreateIntFieldBuilder(System.Object[] attributes, System.Int32 min, System.Int32 max, System.Converter<System.Object, System.Int32> fromObject, System.Converter<System.Int32, System.Object> toObject);
    private static Game.UI.Widgets.FieldBuilder CreateIntFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject, System.Converter<TValue, System.Object> toObject);
    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Fields

- `private static readonly System.Int32 kGlobalValueRange`  

```csharp
private static readonly System.Int32 kGlobalValueRange;
```


## Constructors

- `public IntFieldBuilders()`  

```csharp
public IntFieldBuilders();
```


## Methods

- `internal static <TryCreate>g__FromByte|1_1(System.Int32 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromByte|1_1(System.Int32 value);
```

- `internal static <TryCreate>g__FromInt|1_9(System.Int32 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromInt|1_9(System.Int32 value);
```

- `internal static <TryCreate>g__FromInt2|1_11(Unity.Mathematics.int2 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromInt2|1_11(Unity.Mathematics.int2 value);
```

- `internal static <TryCreate>g__FromInt3|1_15(Unity.Mathematics.int3 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromInt3|1_15(Unity.Mathematics.int3 value);
```

- `internal static <TryCreate>g__FromInt4|1_19(Unity.Mathematics.int4 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromInt4|1_19(Unity.Mathematics.int4 value);
```

- `internal static <TryCreate>g__FromSByte|1_3(System.Int32 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromSByte|1_3(System.Int32 value);
```

- `internal static <TryCreate>g__FromShort|1_5(System.Int32 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromShort|1_5(System.Int32 value);
```

- `internal static <TryCreate>g__FromUShort|1_7(System.Int32 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromUShort|1_7(System.Int32 value);
```

- `internal static <TryCreate>g__FromVector2Int|1_13(Unity.Mathematics.int2 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromVector2Int|1_13(Unity.Mathematics.int2 value);
```

- `internal static <TryCreate>g__FromVector3Int|1_17(Unity.Mathematics.int3 value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromVector3Int|1_17(Unity.Mathematics.int3 value);
```

- `internal static <TryCreate>g__ToByte|1_0(System.Object value) : System.Int32`  

```csharp
internal static System.Int32 <TryCreate>g__ToByte|1_0(System.Object value);
```

- `internal static <TryCreate>g__ToInt|1_8(System.Object value) : System.Int32`  

```csharp
internal static System.Int32 <TryCreate>g__ToInt|1_8(System.Object value);
```

- `internal static <TryCreate>g__ToInt2|1_10(System.Object value) : Unity.Mathematics.int2`  

```csharp
internal static Unity.Mathematics.int2 <TryCreate>g__ToInt2|1_10(System.Object value);
```

- `internal static <TryCreate>g__ToInt3|1_14(System.Object value) : Unity.Mathematics.int3`  

```csharp
internal static Unity.Mathematics.int3 <TryCreate>g__ToInt3|1_14(System.Object value);
```

- `internal static <TryCreate>g__ToInt4|1_18(System.Object value) : Unity.Mathematics.int4`  

```csharp
internal static Unity.Mathematics.int4 <TryCreate>g__ToInt4|1_18(System.Object value);
```

- `internal static <TryCreate>g__ToSByte|1_2(System.Object value) : System.Int32`  

```csharp
internal static System.Int32 <TryCreate>g__ToSByte|1_2(System.Object value);
```

- `internal static <TryCreate>g__ToShort|1_4(System.Object value) : System.Int32`  

```csharp
internal static System.Int32 <TryCreate>g__ToShort|1_4(System.Object value);
```

- `internal static <TryCreate>g__ToUShort|1_6(System.Object value) : System.Int32`  

```csharp
internal static System.Int32 <TryCreate>g__ToUShort|1_6(System.Object value);
```

- `internal static <TryCreate>g__ToVector2Int|1_12(System.Object value) : Unity.Mathematics.int2`  

```csharp
internal static Unity.Mathematics.int2 <TryCreate>g__ToVector2Int|1_12(System.Object value);
```

- `internal static <TryCreate>g__ToVector3Int|1_16(System.Object value) : Unity.Mathematics.int3`  

```csharp
internal static Unity.Mathematics.int3 <TryCreate>g__ToVector3Int|1_16(System.Object value);
```

- `private static CreateIntFieldBuilder(System.Object[] attributes, System.Int32 min, System.Int32 max, System.Converter<System.Object, System.Int32> fromObject, System.Converter<System.Int32, System.Object> toObject) : Game.UI.Widgets.FieldBuilder`  

```csharp
private static FieldBuilder CreateIntFieldBuilder(object[] attributes, int min, int max, Converter<object, int> fromObject, Converter<int, object> toObject)
	{
		if (!EditorGenerator.sBypassValueLimits)
		{
			min = math.max(min, -kGlobalValueRange);
			max = math.min(max, kGlobalValueRange);
		}
		int step = WidgetAttributeUtils.GetNumberStep(attributes, 1);
		if (!EditorGenerator.sBypassValueLimits && WidgetAttributeUtils.GetNumberRange(attributes, ref min, ref max) && !WidgetAttributeUtils.RequiresInputField(attributes))
		{
			string unit = WidgetAttributeUtils.GetNumberUnit(attributes);
			return (IValueAccessor accessor) => new IntSliderField
			{
				min = min,
				max = max,
				step = step,
				unit = unit,
				accessor = new CastAccessor<int>(accessor, fromObject, toObject)
			};
		}
		return (IValueAccessor accessor) => new IntInputField
		{
			min = min,
			max = max,
			step = step,
			accessor = new CastAccessor<int>(accessor, fromObject, toObject)
		};
	}
```

- `private static CreateIntFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject, System.Converter<TValue, System.Object> toObject) : Game.UI.Widgets.FieldBuilder`  

```csharp
private static Game.UI.Widgets.FieldBuilder CreateIntFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject, System.Converter<TValue, System.Object> toObject);
```

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(byte))
		{
			return CreateIntFieldBuilder(attributes, 0, 255, ToByte, FromByte);
		}
		if (memberType == typeof(sbyte))
		{
			return CreateIntFieldBuilder(attributes, -128, 127, ToSByte, FromSByte);
		}
		if (memberType == typeof(short))
		{
			return CreateIntFieldBuilder(attributes, -32768, 32767, ToShort, FromShort);
		}
		if (memberType == typeof(ushort))
		{
			return CreateIntFieldBuilder(attributes, 0, 65535, ToUShort, FromUShort);
		}
		if (memberType == typeof(int))
		{
			return CreateIntFieldBuilder(attributes, int.MinValue, int.MaxValue, ToInt, FromInt);
		}
		if (memberType == typeof(int2))
		{
			return CreateIntFieldBuilder<Int2InputField, int2>(attributes, ToInt2, FromInt2);
		}
		if (memberType == typeof(Vector2Int))
		{
			return CreateIntFieldBuilder<Int2InputField, int2>(attributes, ToVector2Int, FromVector2Int);
		}
		if (memberType == typeof(int3))
		{
			return CreateIntFieldBuilder<Int3InputField, int3>(attributes, ToInt3, FromInt3);
		}
		if (memberType == typeof(Vector3Int))
		{
			return CreateIntFieldBuilder<Int3InputField, int3>(attributes, ToVector3Int, FromVector3Int);
		}
		if (memberType == typeof(int4))
		{
			return CreateIntFieldBuilder<Int4InputField, int4>(attributes, ToInt4, FromInt4);
		}
		return null;
		static object FromByte(int value)
		{
			return (byte)value;
		}
		static object FromInt(int value)
		{
			return value;
		}
		static object FromInt2(int2 value)
		{
			return value;
		}
		static object FromInt3(int3 value)
		{
			return value;
		}
		static object FromInt4(int4 value)
		{
			return value;
		}
		static object FromSByte(int value)
		{
			return (sbyte)value;
		}
		static object FromShort(int value)
		{
			return (short)value;
		}
		static object FromUShort(int value)
		{
			return (ushort)value;
		}
		static object FromVector2Int(int2 value)
		{
			return new Vector2Int(value.x, value.y);
		}
		static object FromVector3Int(int3 value)
		{
			return new Vector3Int(value.x, value.y, value.z);
		}
		static int ToByte(object value)
		{
			return (byte)value;
		}
		static int ToInt(object value)
		{
			return (int)value;
		}
		static int2 ToInt2(object value)
		{
			return (int2)value;
		}
		static int3 ToInt3(object value)
		{
			return (int3)value;
		}
		static int4 ToInt4(object value)
		{
			return (int4)value;
		}
		static int ToSByte(object value)
		{
			return (sbyte)value;
		}
		static int ToShort(object value)
		{
			return (short)value;
		}
		static int ToUShort(object value)
		{
			return (ushort)value;
		}
		static int2 ToVector2Int(object value)
		{
			Vector2Int vector2Int = (Vector2Int)value;
			return new int2(vector2Int.x, vector2Int.y);
		}
		static int3 ToVector3Int(object value)
		{
			Vector3Int vector3Int = (Vector3Int)value;
			return new int3(vector3Int.x, vector3Int.y, vector3Int.z);
		}
	}
```


## Nested types

- `Game.UI.Widgets.IntFieldBuilders+<>c__DisplayClass2_0`  
- `Game.UI.Widgets.IntFieldBuilders+<>c__DisplayClass2_1`  
- `Game.UI.Widgets.IntFieldBuilders+<>c__DisplayClass3_0<TWidget, TValue>`  

