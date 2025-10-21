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
private static Game.UI.Widgets.FieldBuilder CreateColorFieldBuilder(System.Object[] attributes, System.Converter<System.Object, UnityEngine.Color> fromObject, System.Converter<UnityEngine.Color, System.Object> toObject);
```

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
```


## Nested types

- `Game.UI.Widgets.ColorFieldBuilders+<>c__DisplayClass1_0`  

