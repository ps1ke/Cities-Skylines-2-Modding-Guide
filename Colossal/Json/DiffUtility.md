# Colossal.Json.DiffUtility

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class DiffUtility
{
    private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.Json.DiffUtility+EncoderDelegate> kValueEncoders;

    public static Colossal.Json.Variant Diff(System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant DiffConvertible(System.Type converterType, System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template);
    private static Colossal.Json.Variant DiffDictionary(System.Collections.IDictionary sourceDict, System.Collections.IDictionary defaultDict, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant DiffDictionaryByKey(System.Collections.IDictionary sourceDict, System.Collections.IDictionary defaultDict, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant DiffEncodable(Colossal.Json.DiffUtility+EncoderDelegate encoder, System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template);
    private static Colossal.Json.Variant DiffList(System.Collections.IList sourceList, System.Collections.IList defaultList, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant DiffObject(System.Object sourceObject, System.Object defaultObject, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant DiffSet(System.Collections.IEnumerable sourceSet, System.Collections.IEnumerable defaultSet, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant DiffTypedDictionary(System.Collections.IList sourceDict, System.Collections.IList defaultDict, Colossal.Json.ProxyArray template, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant Encode(System.Object obj, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant EncodeBool(System.Object obj);
    private static Colossal.Json.Variant EncodeChar(System.Object obj);
    private static Colossal.Json.Variant EncodeDateTime(System.Object obj);
    private static Colossal.Json.ProxyObject EncodeDictionary(System.Collections.IDictionary dict, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant EncodeEnum(System.Object obj);
    private static Colossal.Json.Variant EncodeGuid(System.Object obj);
    private static Colossal.Json.Variant EncodeIPAddress(System.Object obj);
    private static Colossal.Json.ProxyArray EncodeList(System.Collections.IList list, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant EncodeLogLevel(System.Object obj);
    private static Colossal.Json.Variant EncodeNumber(System.Object obj);
    private static Colossal.Json.ProxyObject EncodeObject(System.Object obj, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.ProxyArray EncodeSet(System.Collections.IEnumerable set, Colossal.Json.DiffUtility+Options options);
    private static Colossal.Json.Variant EncodeString(System.Object obj);
    private static Colossal.Json.Variant EncodeTimeSpan(System.Object obj);
    private static System.Object GetFirstTypedItem(System.Collections.IList list, System.String typeHint);
    private static Colossal.Json.Variant GetFirstTypedItem(Colossal.Json.ProxyArray array, System.String typeHint);
    private static System.Boolean SequenceEqual(System.Collections.IList a, System.Collections.IList b);
    private static System.Boolean SequenceEqual(System.Collections.IEnumerable a, System.Collections.IEnumerable b);
    private static System.Boolean SequenceEqual(System.Collections.IDictionary a, System.Collections.IDictionary b);
    private static System.Void SetOption(Colossal.Json.DiffUtility+Options& options, Colossal.Json.DiffUtility+Options option, System.Boolean enabled);
    private static System.Boolean TryGetValueEncoder(System.Type type, Colossal.Json.DiffUtility+EncoderDelegate& encoder);
}
```


## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.Json.DiffUtility+EncoderDelegate> kValueEncoders`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.Json.DiffUtility+EncoderDelegate> kValueEncoders;
```


## Methods

- `public static Diff(System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template = null, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  

```csharp
public static Colossal.Json.Variant Diff(System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options);
```

- `private static DiffConvertible(System.Type converterType, System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant DiffConvertible(System.Type converterType, System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template);
```

- `private static DiffDictionary(System.Collections.IDictionary sourceDict, System.Collections.IDictionary defaultDict, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant DiffDictionary(System.Collections.IDictionary sourceDict, System.Collections.IDictionary defaultDict, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options);
```

- `private static DiffDictionaryByKey(System.Collections.IDictionary sourceDict, System.Collections.IDictionary defaultDict, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant DiffDictionaryByKey(System.Collections.IDictionary sourceDict, System.Collections.IDictionary defaultDict, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options);
```

- `private static DiffEncodable(Colossal.Json.DiffUtility+EncoderDelegate encoder, System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant DiffEncodable(Colossal.Json.DiffUtility+EncoderDelegate encoder, System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template);
```

- `private static DiffList(System.Collections.IList sourceList, System.Collections.IList defaultList, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant DiffList(System.Collections.IList sourceList, System.Collections.IList defaultList, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options);
```

- `private static DiffObject(System.Object sourceObject, System.Object defaultObject, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant DiffObject(System.Object sourceObject, System.Object defaultObject, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options);
```

- `private static DiffSet(System.Collections.IEnumerable sourceSet, System.Collections.IEnumerable defaultSet, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant DiffSet(System.Collections.IEnumerable sourceSet, System.Collections.IEnumerable defaultSet, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options);
```

- `private static DiffTypedDictionary(System.Collections.IList sourceDict, System.Collections.IList defaultDict, Colossal.Json.ProxyArray template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant DiffTypedDictionary(System.Collections.IList sourceDict, System.Collections.IList defaultDict, Colossal.Json.ProxyArray template, Colossal.Json.DiffUtility+Options options);
```

- `private static Encode(System.Object obj, Colossal.Json.DiffUtility+Options options) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant Encode(System.Object obj, Colossal.Json.DiffUtility+Options options);
```

- `private static EncodeBool(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeBool(System.Object obj);
```

- `private static EncodeChar(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeChar(System.Object obj);
```

- `private static EncodeDateTime(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeDateTime(System.Object obj);
```

- `private static EncodeDictionary(System.Collections.IDictionary dict, Colossal.Json.DiffUtility+Options options) : Colossal.Json.ProxyObject`  

```csharp
private static Colossal.Json.ProxyObject EncodeDictionary(System.Collections.IDictionary dict, Colossal.Json.DiffUtility+Options options);
```

- `private static EncodeEnum(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeEnum(System.Object obj);
```

- `private static EncodeGuid(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeGuid(System.Object obj);
```

- `private static EncodeIPAddress(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeIPAddress(System.Object obj);
```

- `private static EncodeList(System.Collections.IList list, Colossal.Json.DiffUtility+Options options) : Colossal.Json.ProxyArray`  

```csharp
private static Colossal.Json.ProxyArray EncodeList(System.Collections.IList list, Colossal.Json.DiffUtility+Options options);
```

- `private static EncodeLogLevel(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeLogLevel(System.Object obj);
```

- `private static EncodeNumber(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeNumber(System.Object obj);
```

- `private static EncodeObject(System.Object obj, Colossal.Json.DiffUtility+Options options) : Colossal.Json.ProxyObject`  

```csharp
private static Colossal.Json.ProxyObject EncodeObject(System.Object obj, Colossal.Json.DiffUtility+Options options);
```

- `private static EncodeSet(System.Collections.IEnumerable set, Colossal.Json.DiffUtility+Options options) : Colossal.Json.ProxyArray`  

```csharp
private static Colossal.Json.ProxyArray EncodeSet(System.Collections.IEnumerable set, Colossal.Json.DiffUtility+Options options);
```

- `private static EncodeString(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeString(System.Object obj);
```

- `private static EncodeTimeSpan(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant EncodeTimeSpan(System.Object obj);
```

- `private static GetFirstTypedItem(System.Collections.IList list, System.String typeHint) : System.Object`  

```csharp
private static System.Object GetFirstTypedItem(System.Collections.IList list, System.String typeHint);
```

- `private static GetFirstTypedItem(Colossal.Json.ProxyArray array, System.String typeHint) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant GetFirstTypedItem(Colossal.Json.ProxyArray array, System.String typeHint);
```

- `private static SequenceEqual(System.Collections.IList a, System.Collections.IList b) : System.Boolean`  

```csharp
private static System.Boolean SequenceEqual(System.Collections.IList a, System.Collections.IList b);
```

- `private static SequenceEqual(System.Collections.IEnumerable a, System.Collections.IEnumerable b) : System.Boolean`  

```csharp
private static System.Boolean SequenceEqual(System.Collections.IEnumerable a, System.Collections.IEnumerable b);
```

- `private static SequenceEqual(System.Collections.IDictionary a, System.Collections.IDictionary b) : System.Boolean`  

```csharp
private static System.Boolean SequenceEqual(System.Collections.IDictionary a, System.Collections.IDictionary b);
```

- `private static SetOption(Colossal.Json.DiffUtility+Options& options, Colossal.Json.DiffUtility+Options option, System.Boolean enabled) : System.Void`  

```csharp
private static System.Void SetOption(Colossal.Json.DiffUtility+Options& options, Colossal.Json.DiffUtility+Options option, System.Boolean enabled);
```

- `private static TryGetValueEncoder(System.Type type, Colossal.Json.DiffUtility+EncoderDelegate& encoder) : System.Boolean`  

```csharp
private static System.Boolean TryGetValueEncoder(System.Type type, Colossal.Json.DiffUtility+EncoderDelegate& encoder);
```


## Nested types

- `Colossal.Json.DiffUtility+Options`  
- `Colossal.Json.DiffUtility+EncoderDelegate`  
- `Colossal.Json.DiffUtility+<>c`  
- `Colossal.Json.DiffUtility+<>c__DisplayClass27_0`  
- `Colossal.Json.DiffUtility+<>c__DisplayClass9_0`  

