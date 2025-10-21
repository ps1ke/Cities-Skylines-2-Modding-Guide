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
private static Game.UI.Widgets.FieldBuilder CreateIntFieldBuilder(System.Object[] attributes, System.Int32 min, System.Int32 max, System.Converter<System.Object, System.Int32> fromObject, System.Converter<System.Int32, System.Object> toObject);
```

- `private static CreateIntFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject, System.Converter<TValue, System.Object> toObject) : Game.UI.Widgets.FieldBuilder`  

```csharp
private static Game.UI.Widgets.FieldBuilder CreateIntFieldBuilder<TWidget, TValue>(System.Object[] attributes, System.Converter<System.Object, TValue> fromObject, System.Converter<TValue, System.Object> toObject);
```

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
```


## Nested types

- `Game.UI.Widgets.IntFieldBuilders+<>c__DisplayClass2_0`  
- `Game.UI.Widgets.IntFieldBuilders+<>c__DisplayClass2_1`  
- `Game.UI.Widgets.IntFieldBuilders+<>c__DisplayClass3_0<TWidget, TValue>`  

