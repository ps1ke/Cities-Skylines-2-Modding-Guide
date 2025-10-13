# Colossal.Json.Extensions

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class Extensions
{
    private static readonly System.Collections.Generic.List<System.String> kValueProperties;
    private static readonly System.Collections.Generic.List<System.String> kVector2Properties;
    private static readonly System.Collections.Generic.List<System.String> kVector3Properties;
    private static readonly System.Collections.Generic.List<System.String> kVector4Properties;
    private static readonly System.Collections.Generic.List<System.String> kMatrix2Properties;
    private static readonly System.Collections.Generic.List<System.String> kMatrix3Properties;
    private static readonly System.Collections.Generic.List<System.String> kMatrix4Properties;
    private static readonly System.Collections.Generic.List<System.String> kMatrix4x4Properties;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> kPropertiesConstants;
    private static readonly System.Type includeAttrType;
    private static readonly System.Type excludeAttrType;
    private static readonly System.Type typeHintAttrType;
    private static const System.Reflection.BindingFlags kHierarchyBindingFlags;
    private static const System.Reflection.BindingFlags kBindingFlags;

    public static System.Boolean AnyOfType<TSource>(System.Collections.Generic.IEnumerable<TSource> source, System.Type expectedType);
    public static System.Void ForEachField(System.Type type, Colossal.Json.EncodeOptions options, Colossal.Json.Extensions+MemberDelegate<System.Reflection.FieldInfo> action);
    public static System.Void ForEachProperty(System.Type type, Colossal.Json.EncodeOptions options, Colossal.Json.Extensions+MemberDelegate<System.Reflection.PropertyInfo> action);
    public static System.String ToJSONString<T>(T settings, Colossal.Json.EncodeOptions encodeOptions);
}
```


## Fields

- `private static readonly System.Collections.Generic.List<System.String> kValueProperties`  

```csharp
private static readonly System.Collections.Generic.List<System.String> kValueProperties;
```

- `private static readonly System.Collections.Generic.List<System.String> kVector2Properties`  

```csharp
private static readonly System.Collections.Generic.List<System.String> kVector2Properties;
```

- `private static readonly System.Collections.Generic.List<System.String> kVector3Properties`  

```csharp
private static readonly System.Collections.Generic.List<System.String> kVector3Properties;
```

- `private static readonly System.Collections.Generic.List<System.String> kVector4Properties`  

```csharp
private static readonly System.Collections.Generic.List<System.String> kVector4Properties;
```

- `private static readonly System.Collections.Generic.List<System.String> kMatrix2Properties`  

```csharp
private static readonly System.Collections.Generic.List<System.String> kMatrix2Properties;
```

- `private static readonly System.Collections.Generic.List<System.String> kMatrix3Properties`  

```csharp
private static readonly System.Collections.Generic.List<System.String> kMatrix3Properties;
```

- `private static readonly System.Collections.Generic.List<System.String> kMatrix4Properties`  

```csharp
private static readonly System.Collections.Generic.List<System.String> kMatrix4Properties;
```

- `private static readonly System.Collections.Generic.List<System.String> kMatrix4x4Properties`  

```csharp
private static readonly System.Collections.Generic.List<System.String> kMatrix4x4Properties;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> kPropertiesConstants`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> kPropertiesConstants;
```

- `private static readonly System.Type includeAttrType`  

```csharp
private static readonly System.Type includeAttrType;
```

- `private static readonly System.Type excludeAttrType`  

```csharp
private static readonly System.Type excludeAttrType;
```

- `private static readonly System.Type typeHintAttrType`  

```csharp
private static readonly System.Type typeHintAttrType;
```

- `private static const System.Reflection.BindingFlags kHierarchyBindingFlags`  

```csharp
private static const System.Reflection.BindingFlags kHierarchyBindingFlags;
```

- `private static const System.Reflection.BindingFlags kBindingFlags`  

```csharp
private static const System.Reflection.BindingFlags kBindingFlags;
```


## Methods

- `public static AnyOfType<TSource>(System.Collections.Generic.IEnumerable<TSource> source, System.Type expectedType) : System.Boolean`  

```csharp
public static System.Boolean AnyOfType<TSource>(System.Collections.Generic.IEnumerable<TSource> source, System.Type expectedType);
```

- `public static ForEachField(System.Type type, Colossal.Json.EncodeOptions options, Colossal.Json.Extensions+MemberDelegate<System.Reflection.FieldInfo> action) : System.Void`  

```csharp
public static System.Void ForEachField(System.Type type, Colossal.Json.EncodeOptions options, Colossal.Json.Extensions+MemberDelegate<System.Reflection.FieldInfo> action);
```

- `public static ForEachProperty(System.Type type, Colossal.Json.EncodeOptions options, Colossal.Json.Extensions+MemberDelegate<System.Reflection.PropertyInfo> action) : System.Void`  

```csharp
public static System.Void ForEachProperty(System.Type type, Colossal.Json.EncodeOptions options, Colossal.Json.Extensions+MemberDelegate<System.Reflection.PropertyInfo> action);
```

- `public static ToJSONString<T>(T settings, Colossal.Json.EncodeOptions encodeOptions = CompactPrint, IgnoreSetters) : System.String`  

```csharp
public static System.String ToJSONString<T>(T settings, Colossal.Json.EncodeOptions encodeOptions);
```


## Nested types

- `Colossal.Json.Extensions+MemberDelegate<T>`  

