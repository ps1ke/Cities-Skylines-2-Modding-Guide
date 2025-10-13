# Game.UI.Widgets.WidgetReflectionUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class WidgetReflectionUtils
{
    private static Colossal.OdinSerializer.CustomSerializationPolicy kListElementLabelPolicy;

    public static Game.UI.Widgets.FieldBuilder CreateFieldBuilder<T, U>();
    public static Game.UI.Widgets.FieldBuilder CreateFieldBuilder<T, U>(System.Converter<System.Object, U> fromObject, System.Converter<U, System.Object> toObject);
    public static System.Reflection.MemberInfo GetListElementLabelMember(System.Type type);
    public static System.Type GetListElementType(System.Type memberType);
    private static System.Boolean IsGenericListInterface(System.Type type);
    public static System.Boolean IsListType(System.Type memberType);
    public static System.String NicifyVariableName(System.String name);
}
```


## Fields

- `private static Colossal.OdinSerializer.CustomSerializationPolicy kListElementLabelPolicy`  

```csharp
private static Colossal.OdinSerializer.CustomSerializationPolicy kListElementLabelPolicy;
```


## Methods

- `public static CreateFieldBuilder<T, U>() : Game.UI.Widgets.FieldBuilder`  

```csharp
public static Game.UI.Widgets.FieldBuilder CreateFieldBuilder<T, U>();
```

- `public static CreateFieldBuilder<T, U>(System.Converter<System.Object, U> fromObject, System.Converter<U, System.Object> toObject) : Game.UI.Widgets.FieldBuilder`  

```csharp
public static Game.UI.Widgets.FieldBuilder CreateFieldBuilder<T, U>(System.Converter<System.Object, U> fromObject, System.Converter<U, System.Object> toObject);
```

- `public static GetListElementLabelMember(System.Type type) : System.Reflection.MemberInfo`  

```csharp
public static System.Reflection.MemberInfo GetListElementLabelMember(System.Type type);
```

- `public static GetListElementType(System.Type memberType) : System.Type`  

```csharp
public static System.Type GetListElementType(System.Type memberType);
```

- `private static IsGenericListInterface(System.Type type) : System.Boolean`  

```csharp
private static System.Boolean IsGenericListInterface(System.Type type);
```

- `public static IsListType(System.Type memberType) : System.Boolean`  

```csharp
public static System.Boolean IsListType(System.Type memberType);
```

- `public static NicifyVariableName(System.String name) : System.String`  

```csharp
public static System.String NicifyVariableName(System.String name);
```


## Nested types

- `Game.UI.Widgets.WidgetReflectionUtils+<>c`  
- `Game.UI.Widgets.WidgetReflectionUtils+<>c__3<T, U>`  
- `Game.UI.Widgets.WidgetReflectionUtils+<>c__DisplayClass4_0<T, U>`  

