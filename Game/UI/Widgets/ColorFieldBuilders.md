# Game.UI.Widgets.ColorFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class ColorFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public ColorFieldBuilders();

    internal static System.Object <TryCreate>g__FromColor|0_1(UnityEngine.Color value);
    internal static System.Object <TryCreate>g__FromColor32|0_3(UnityEngine.Color value);
    internal static UnityEngine.Color <TryCreate>g__ToColor|0_0(System.Object value);
    internal static UnityEngine.Color <TryCreate>g__ToColor32|0_2(System.Object value);
    private static Game.UI.Widgets.FieldBuilder CreateColorFieldBuilder(System.Object[] attributes, System.Converter<System.Object, UnityEngine.Color> fromObject, System.Converter<UnityEngine.Color, System.Object> toObject);
    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public ColorFieldBuilders()`  

```csharp
public ColorFieldBuilders();
```


## Methods

- `internal static <TryCreate>g__FromColor|0_1(UnityEngine.Color value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromColor|0_1(UnityEngine.Color value);
```

- `internal static <TryCreate>g__FromColor32|0_3(UnityEngine.Color value) : System.Object`  

```csharp
internal static System.Object <TryCreate>g__FromColor32|0_3(UnityEngine.Color value);
```

- `internal static <TryCreate>g__ToColor|0_0(System.Object value) : UnityEngine.Color`  

```csharp
internal static UnityEngine.Color <TryCreate>g__ToColor|0_0(System.Object value);
```

- `internal static <TryCreate>g__ToColor32|0_2(System.Object value) : UnityEngine.Color`  

```csharp
internal static UnityEngine.Color <TryCreate>g__ToColor32|0_2(System.Object value);
```

- `private static CreateColorFieldBuilder(System.Object[] attributes, System.Converter<System.Object, UnityEngine.Color> fromObject, System.Converter<UnityEngine.Color, System.Object> toObject) : Game.UI.Widgets.FieldBuilder`  

```csharp
private static FieldBuilder CreateColorFieldBuilder(object[] attributes, Converter<object, Color> fromObject, Converter<Color, object> toObject)
	{
		bool hdr = false;
		bool showAlpha = false;
		WidgetAttributeUtils.GetColorUsage(attributes, ref hdr, ref showAlpha);
		return (IValueAccessor accessor) => new ColorField
		{
			hdr = hdr,
			showAlpha = showAlpha,
			accessor = new CastAccessor<Color>(accessor, fromObject, toObject)
		};
	}
```

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		if (memberType == typeof(Color))
		{
			return CreateColorFieldBuilder(attributes, ToColor, FromColor);
		}
		if (memberType == typeof(Color32))
		{
			return CreateColorFieldBuilder(attributes, ToColor32, FromColor32);
		}
		return null;
		static object FromColor(Color value)
		{
			return value;
		}
		static object FromColor32(Color value)
		{
			return (Color32)value;
		}
		static Color ToColor(object value)
		{
			return (Color)value;
		}
		static Color ToColor32(object value)
		{
			return (Color32)value;
		}
	}
```


## Nested types

- `Game.UI.Widgets.ColorFieldBuilders+<>c__DisplayClass1_0`  

