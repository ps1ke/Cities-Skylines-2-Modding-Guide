# Colossal.Json.JSON

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class JSON
{
    private static readonly System.Type includeAttrType;
    private static readonly System.Type excludeAttrType;
    private static readonly System.Type decodeAliasAttrType;
    private static readonly System.Type typedDictAttrType;
    private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> typeCache;
    private static readonly System.Reflection.MethodInfo decodeTypeInPlaceMethod;
    private static readonly System.Reflection.MethodInfo decodeListMethod;
    private static readonly System.Reflection.MethodInfo decodeTypedDictListMethod;
    private static readonly System.Reflection.MethodInfo decodeDictionaryMethod;
    private static readonly System.Reflection.MethodInfo decodeArrayMethod;
    private static readonly System.Reflection.MethodInfo decodeTypedDictArrayMethod;
    private static readonly System.Reflection.MethodInfo decodeMultiRankArrayMethod;
    private static readonly System.Reflection.MethodInfo decodeSetMethod;
    private static const System.Reflection.BindingFlags instanceBindingFlags;
    private static const System.Reflection.BindingFlags staticBindingFlags;

    private static System.Void DecodeArray<T>(Colossal.Json.Variant data, T[]& array, System.Boolean discardExtraItems);
    private static System.Void DecodeDictionary<TDic, TKey, TValue>(Colossal.Json.Variant data, TDic& dict);
    private static System.Void DecodeList<T>(Colossal.Json.Variant data, List`1& list, System.Boolean discardExtraItems);
    private static System.Void DecodeMultiRankArray<T>(Colossal.Json.ProxyArray arrayData, System.Array array, System.Int32 arrayRank, System.Int32[] indices);
    private static System.Void DecodeObject<T>(Colossal.Json.ProxyObject data, T& item, System.Type type);
    private static System.Void DecodeSet<TSet, TElement>(Colossal.Json.Variant data, TSet& set);
    private static T DecodeType<T>(Colossal.Json.Variant data);
    private static System.Void DecodeTypedDictionary<T>(Colossal.Json.Variant data, System.Collections.Generic.List<T> list);
    private static System.Void DecodeTypedDictionaryArray<T>(Colossal.Json.Variant data, T[]& array);
    private static System.Void DecodeTypedDictionaryList<T>(Colossal.Json.Variant data, List`1& list);
    private static System.Void DecodeTypeInPlace<T>(Colossal.Json.Variant data, T& item, System.Type type, Colossal.Json.JSON+DecodeOptions options);
    public static System.Void DictKeySupportTypeForAOT<T>();
    public static System.Void DictSupportTypeForAOT<TKey, TValue>();
    public static System.String Dump(System.Object data, Colossal.Json.EncodeOptions options);
    private static T FindDecodeAlias<T>(System.Collections.Generic.IEnumerable<T> members, System.String name);
    private static System.Type FindType(System.String fullName);
    private static System.Reflection.FieldInfo GetField(System.Type type, System.String field);
    private static T GetFirstTypedItem<T>(System.Collections.Generic.List<T> list, System.Type type);
    public static Colossal.Json.Variant Load(System.String json);
    public static System.Void MakeInto<T>(Colossal.Json.Variant data, T& item);
    public static T MakeInto<T>(Colossal.Json.Variant data);
    public static System.Void SupportTypeForAOT<T>();
    private static System.Void SupportValueTypesForAOT();
    private static System.Boolean TryGetDecodableMember(System.Type type, System.String name, System.Reflection.MemberInfo& member);
    public static System.Void WriteInto<T>(Colossal.Json.Variant data, T& item);
    public static System.Void WriteInto<T>(Colossal.Json.Variant data, T item);
}
```


## Fields

- `private static readonly System.Type includeAttrType`  

```csharp
private static readonly System.Type includeAttrType;
```

- `private static readonly System.Type excludeAttrType`  

```csharp
private static readonly System.Type excludeAttrType;
```

- `private static readonly System.Type decodeAliasAttrType`  

```csharp
private static readonly System.Type decodeAliasAttrType;
```

- `private static readonly System.Type typedDictAttrType`  

```csharp
private static readonly System.Type typedDictAttrType;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> typeCache`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> typeCache;
```

- `private static readonly System.Reflection.MethodInfo decodeTypeInPlaceMethod`  

```csharp
private static readonly System.Reflection.MethodInfo decodeTypeInPlaceMethod;
```

- `private static readonly System.Reflection.MethodInfo decodeListMethod`  

```csharp
private static readonly System.Reflection.MethodInfo decodeListMethod;
```

- `private static readonly System.Reflection.MethodInfo decodeTypedDictListMethod`  

```csharp
private static readonly System.Reflection.MethodInfo decodeTypedDictListMethod;
```

- `private static readonly System.Reflection.MethodInfo decodeDictionaryMethod`  

```csharp
private static readonly System.Reflection.MethodInfo decodeDictionaryMethod;
```

- `private static readonly System.Reflection.MethodInfo decodeArrayMethod`  

```csharp
private static readonly System.Reflection.MethodInfo decodeArrayMethod;
```

- `private static readonly System.Reflection.MethodInfo decodeTypedDictArrayMethod`  

```csharp
private static readonly System.Reflection.MethodInfo decodeTypedDictArrayMethod;
```

- `private static readonly System.Reflection.MethodInfo decodeMultiRankArrayMethod`  

```csharp
private static readonly System.Reflection.MethodInfo decodeMultiRankArrayMethod;
```

- `private static readonly System.Reflection.MethodInfo decodeSetMethod`  

```csharp
private static readonly System.Reflection.MethodInfo decodeSetMethod;
```

- `private static const System.Reflection.BindingFlags instanceBindingFlags`  

```csharp
private static const System.Reflection.BindingFlags instanceBindingFlags;
```

- `private static const System.Reflection.BindingFlags staticBindingFlags`  

```csharp
private static const System.Reflection.BindingFlags staticBindingFlags;
```


## Methods

- `private static DecodeArray<T>(Colossal.Json.Variant data, T[]& array, System.Boolean discardExtraItems) : System.Void`  

```csharp
private static System.Void DecodeArray<T>(Colossal.Json.Variant data, T[]& array, System.Boolean discardExtraItems);
```

- `private static DecodeDictionary<TDic, TKey, TValue>(Colossal.Json.Variant data, TDic& dict) : System.Void`  

```csharp
private static System.Void DecodeDictionary<TDic, TKey, TValue>(Colossal.Json.Variant data, TDic& dict);
```

- `private static DecodeList<T>(Colossal.Json.Variant data, List`1& list, System.Boolean discardExtraItems) : System.Void`  

```csharp
private static System.Void DecodeList<T>(Colossal.Json.Variant data, List`1& list, System.Boolean discardExtraItems);
```

- `private static DecodeMultiRankArray<T>(Colossal.Json.ProxyArray arrayData, System.Array array, System.Int32 arrayRank, System.Int32[] indices) : System.Void`  

```csharp
private static System.Void DecodeMultiRankArray<T>(Colossal.Json.ProxyArray arrayData, System.Array array, System.Int32 arrayRank, System.Int32[] indices);
```

- `private static DecodeObject<T>(Colossal.Json.ProxyObject data, T& item, System.Type type) : System.Void`  

```csharp
private static System.Void DecodeObject<T>(Colossal.Json.ProxyObject data, T& item, System.Type type);
```

- `private static DecodeSet<TSet, TElement>(Colossal.Json.Variant data, TSet& set) : System.Void`  

```csharp
private static System.Void DecodeSet<TSet, TElement>(Colossal.Json.Variant data, TSet& set);
```

- `private static DecodeType<T>(Colossal.Json.Variant data) : T`  

```csharp
private static T DecodeType<T>(Colossal.Json.Variant data);
```

- `private static DecodeTypedDictionary<T>(Colossal.Json.Variant data, System.Collections.Generic.List<T> list) : System.Void`  

```csharp
private static System.Void DecodeTypedDictionary<T>(Colossal.Json.Variant data, System.Collections.Generic.List<T> list);
```

- `private static DecodeTypedDictionaryArray<T>(Colossal.Json.Variant data, T[]& array) : System.Void`  

```csharp
private static System.Void DecodeTypedDictionaryArray<T>(Colossal.Json.Variant data, T[]& array);
```

- `private static DecodeTypedDictionaryList<T>(Colossal.Json.Variant data, List`1& list) : System.Void`  

```csharp
private static System.Void DecodeTypedDictionaryList<T>(Colossal.Json.Variant data, List`1& list);
```

- `private static DecodeTypeInPlace<T>(Colossal.Json.Variant data, T& item, System.Type type, Colossal.Json.JSON+DecodeOptions options = None) : System.Void`  

```csharp
private static System.Void DecodeTypeInPlace<T>(Colossal.Json.Variant data, T& item, System.Type type, Colossal.Json.JSON+DecodeOptions options);
```

- `public static DictKeySupportTypeForAOT<T>() : System.Void`  

```csharp
public static System.Void DictKeySupportTypeForAOT<T>();
```

- `public static DictSupportTypeForAOT<TKey, TValue>() : System.Void`  

```csharp
public static System.Void DictSupportTypeForAOT<TKey, TValue>();
```

- `public static Dump(System.Object data, Colossal.Json.EncodeOptions options = None) : System.String`  

```csharp
public static System.String Dump(System.Object data, Colossal.Json.EncodeOptions options);
```

- `private static FindDecodeAlias<T>(System.Collections.Generic.IEnumerable<T> members, System.String name) : T`  

```csharp
private static T FindDecodeAlias<T>(System.Collections.Generic.IEnumerable<T> members, System.String name);
```

- `private static FindType(System.String fullName) : System.Type`  

```csharp
private static System.Type FindType(System.String fullName);
```

- `private static GetField(System.Type type, System.String field) : System.Reflection.FieldInfo`  

```csharp
private static System.Reflection.FieldInfo GetField(System.Type type, System.String field);
```

- `private static GetFirstTypedItem<T>(System.Collections.Generic.List<T> list, System.Type type) : T`  

```csharp
private static T GetFirstTypedItem<T>(System.Collections.Generic.List<T> list, System.Type type);
```

- `public static Load(System.String json) : Colossal.Json.Variant`  

```csharp
public static Colossal.Json.Variant Load(System.String json);
```

- `public static MakeInto<T>(Colossal.Json.Variant data, T& item) : System.Void`  

```csharp
public static System.Void MakeInto<T>(Colossal.Json.Variant data, T& item);
```

- `public static MakeInto<T>(Colossal.Json.Variant data) : T`  

```csharp
public static T MakeInto<T>(Colossal.Json.Variant data);
```

- `public static SupportTypeForAOT<T>() : System.Void`  

```csharp
public static System.Void SupportTypeForAOT<T>();
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static System.Void SupportValueTypesForAOT();
```

- `private static TryGetDecodableMember(System.Type type, System.String name, System.Reflection.MemberInfo& member) : System.Boolean`  

```csharp
private static System.Boolean TryGetDecodableMember(System.Type type, System.String name, System.Reflection.MemberInfo& member);
```

- `public static WriteInto<T>(Colossal.Json.Variant data, T& item) : System.Void`  

```csharp
public static System.Void WriteInto<T>(Colossal.Json.Variant data, T& item);
```

- `public static WriteInto<T>(Colossal.Json.Variant data, T item) : System.Void`  

```csharp
public static System.Void WriteInto<T>(Colossal.Json.Variant data, T item);
```


## Nested types

- `Colossal.Json.JSON+DecodeOptions`  

