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
private static Game.UI.Widgets.FieldBuilder CreateFloatFieldBuilder(System.Object[] attributes, System.Double min, System.Double max, System.Converter<System.Object, System.Double> fromObject, System.Converter<System.Double, System.Object> toObject);
```

- `private static CreateFloatFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject = null, System.Converter<TValue, System.Object> toObject = null) : Game.UI.Widgets.FieldBuilder`  

```csharp
private static Game.UI.Widgets.FieldBuilder CreateFloatFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject, System.Converter<TValue, System.Object> toObject);
```

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
```


## Nested types

- `Game.UI.Widgets.FloatFieldBuilders+<>c__DisplayClass2_0`  
- `Game.UI.Widgets.FloatFieldBuilders+<>c__DisplayClass2_1`  
- `Game.UI.Widgets.FloatFieldBuilders+<>c__DisplayClass3_0<TWidget, TValue>`  

