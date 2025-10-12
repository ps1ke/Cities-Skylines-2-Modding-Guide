# Colossal.Json.Extensions

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Fields

- `private static readonly System.Collections.Generic.List<System.String> kValueProperties`  
- `private static readonly System.Collections.Generic.List<System.String> kVector2Properties`  
- `private static readonly System.Collections.Generic.List<System.String> kVector3Properties`  
- `private static readonly System.Collections.Generic.List<System.String> kVector4Properties`  
- `private static readonly System.Collections.Generic.List<System.String> kMatrix2Properties`  
- `private static readonly System.Collections.Generic.List<System.String> kMatrix3Properties`  
- `private static readonly System.Collections.Generic.List<System.String> kMatrix4Properties`  
- `private static readonly System.Collections.Generic.List<System.String> kMatrix4x4Properties`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> kPropertiesConstants`  
- `private static readonly System.Type includeAttrType`  
- `private static readonly System.Type excludeAttrType`  
- `private static readonly System.Type typeHintAttrType`  
- `private static const System.Reflection.BindingFlags kHierarchyBindingFlags`  
- `private static const System.Reflection.BindingFlags kBindingFlags`  

## Methods

- `public static AnyOfType<TSource>(System.Collections.Generic.IEnumerable<TSource> source, System.Type expectedType) : System.Boolean`  
- `public static ForEachField(System.Type type, Colossal.Json.EncodeOptions options, Colossal.Json.Extensions+MemberDelegate<System.Reflection.FieldInfo> action) : System.Void`  
- `public static ForEachProperty(System.Type type, Colossal.Json.EncodeOptions options, Colossal.Json.Extensions+MemberDelegate<System.Reflection.PropertyInfo> action) : System.Void`  
- `public static ToJSONString<T>(T settings, Colossal.Json.EncodeOptions encodeOptions = CompactPrint, IgnoreSetters) : System.String`  

## Nested types

- `Colossal.Json.Extensions+MemberDelegate<T>`  

