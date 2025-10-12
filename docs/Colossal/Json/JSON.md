# Colossal.Json.JSON

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.Type includeAttrType`  
- `private static readonly System.Type excludeAttrType`  
- `private static readonly System.Type decodeAliasAttrType`  
- `private static readonly System.Type typedDictAttrType`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> typeCache`  
- `private static readonly System.Reflection.MethodInfo decodeTypeInPlaceMethod`  
- `private static readonly System.Reflection.MethodInfo decodeListMethod`  
- `private static readonly System.Reflection.MethodInfo decodeTypedDictListMethod`  
- `private static readonly System.Reflection.MethodInfo decodeDictionaryMethod`  
- `private static readonly System.Reflection.MethodInfo decodeArrayMethod`  
- `private static readonly System.Reflection.MethodInfo decodeTypedDictArrayMethod`  
- `private static readonly System.Reflection.MethodInfo decodeMultiRankArrayMethod`  
- `private static readonly System.Reflection.MethodInfo decodeSetMethod`  
- `private static const System.Reflection.BindingFlags instanceBindingFlags`  
- `private static const System.Reflection.BindingFlags staticBindingFlags`  

## Methods

- `private static DecodeArray<T>(Colossal.Json.Variant data, T[]& array, System.Boolean discardExtraItems) : System.Void`  
- `private static DecodeDictionary<TDic, TKey, TValue>(Colossal.Json.Variant data, TDic& dict) : System.Void`  
- `private static DecodeList<T>(Colossal.Json.Variant data, List`1& list, System.Boolean discardExtraItems) : System.Void`  
- `private static DecodeMultiRankArray<T>(Colossal.Json.ProxyArray arrayData, System.Array array, System.Int32 arrayRank, System.Int32[] indices) : System.Void`  
- `private static DecodeObject<T>(Colossal.Json.ProxyObject data, T& item, System.Type type) : System.Void`  
- `private static DecodeSet<TSet, TElement>(Colossal.Json.Variant data, TSet& set) : System.Void`  
- `private static DecodeType<T>(Colossal.Json.Variant data) : T`  
- `private static DecodeTypedDictionary<T>(Colossal.Json.Variant data, System.Collections.Generic.List<T> list) : System.Void`  
- `private static DecodeTypedDictionaryArray<T>(Colossal.Json.Variant data, T[]& array) : System.Void`  
- `private static DecodeTypedDictionaryList<T>(Colossal.Json.Variant data, List`1& list) : System.Void`  
- `private static DecodeTypeInPlace<T>(Colossal.Json.Variant data, T& item, System.Type type, Colossal.Json.JSON+DecodeOptions options = None) : System.Void`  
- `public static DictKeySupportTypeForAOT<T>() : System.Void`  
- `public static DictSupportTypeForAOT<TKey, TValue>() : System.Void`  
- `public static Dump(System.Object data, Colossal.Json.EncodeOptions options = None) : System.String`  
- `private static FindDecodeAlias<T>(System.Collections.Generic.IEnumerable<T> members, System.String name) : T`  
- `private static FindType(System.String fullName) : System.Type`  
- `private static GetField(System.Type type, System.String field) : System.Reflection.FieldInfo`  
- `private static GetFirstTypedItem<T>(System.Collections.Generic.List<T> list, System.Type type) : T`  
- `public static Load(System.String json) : Colossal.Json.Variant`  
- `public static MakeInto<T>(Colossal.Json.Variant data, T& item) : System.Void`  
- `public static MakeInto<T>(Colossal.Json.Variant data) : T`  
- `public static SupportTypeForAOT<T>() : System.Void`  
- `private static SupportValueTypesForAOT() : System.Void`  
- `private static TryGetDecodableMember(System.Type type, System.String name, System.Reflection.MemberInfo& member) : System.Boolean`  
- `public static WriteInto<T>(Colossal.Json.Variant data, T& item) : System.Void`  
- `public static WriteInto<T>(Colossal.Json.Variant data, T item) : System.Void`  

## Nested types

- `Colossal.Json.JSON+DecodeOptions`  

