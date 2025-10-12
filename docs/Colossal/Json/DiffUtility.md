# Colossal.Json.DiffUtility

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.Json.DiffUtility+EncoderDelegate> kValueEncoders`  

## Methods

- `public static Diff(System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template = null, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  
- `private static DiffConvertible(System.Type converterType, System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template) : Colossal.Json.Variant`  
- `private static DiffDictionary(System.Collections.IDictionary sourceDict, System.Collections.IDictionary defaultDict, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  
- `private static DiffDictionaryByKey(System.Collections.IDictionary sourceDict, System.Collections.IDictionary defaultDict, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  
- `private static DiffEncodable(Colossal.Json.DiffUtility+EncoderDelegate encoder, System.Object sourceObject, System.Object defaultObject, Colossal.Json.Variant template) : Colossal.Json.Variant`  
- `private static DiffList(System.Collections.IList sourceList, System.Collections.IList defaultList, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  
- `private static DiffObject(System.Object sourceObject, System.Object defaultObject, Colossal.Json.ProxyObject template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  
- `private static DiffSet(System.Collections.IEnumerable sourceSet, System.Collections.IEnumerable defaultSet, Colossal.Json.Variant template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  
- `private static DiffTypedDictionary(System.Collections.IList sourceDict, System.Collections.IList defaultDict, Colossal.Json.ProxyArray template, Colossal.Json.DiffUtility+Options options = None) : Colossal.Json.Variant`  
- `private static Encode(System.Object obj, Colossal.Json.DiffUtility+Options options) : Colossal.Json.Variant`  
- `private static EncodeBool(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeChar(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeDateTime(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeDictionary(System.Collections.IDictionary dict, Colossal.Json.DiffUtility+Options options) : Colossal.Json.ProxyObject`  
- `private static EncodeEnum(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeGuid(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeIPAddress(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeList(System.Collections.IList list, Colossal.Json.DiffUtility+Options options) : Colossal.Json.ProxyArray`  
- `private static EncodeLogLevel(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeNumber(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeObject(System.Object obj, Colossal.Json.DiffUtility+Options options) : Colossal.Json.ProxyObject`  
- `private static EncodeSet(System.Collections.IEnumerable set, Colossal.Json.DiffUtility+Options options) : Colossal.Json.ProxyArray`  
- `private static EncodeString(System.Object obj) : Colossal.Json.Variant`  
- `private static EncodeTimeSpan(System.Object obj) : Colossal.Json.Variant`  
- `private static GetFirstTypedItem(System.Collections.IList list, System.String typeHint) : System.Object`  
- `private static GetFirstTypedItem(Colossal.Json.ProxyArray array, System.String typeHint) : Colossal.Json.Variant`  
- `private static SequenceEqual(System.Collections.IList a, System.Collections.IList b) : System.Boolean`  
- `private static SequenceEqual(System.Collections.IEnumerable a, System.Collections.IEnumerable b) : System.Boolean`  
- `private static SequenceEqual(System.Collections.IDictionary a, System.Collections.IDictionary b) : System.Boolean`  
- `private static SetOption(Colossal.Json.DiffUtility+Options& options, Colossal.Json.DiffUtility+Options option, System.Boolean enabled) : System.Void`  
- `private static TryGetValueEncoder(System.Type type, Colossal.Json.DiffUtility+EncoderDelegate& encoder) : System.Boolean`  

## Nested types

- `Colossal.Json.DiffUtility+Options`  
- `Colossal.Json.DiffUtility+EncoderDelegate`  
- `Colossal.Json.DiffUtility+<>c`  
- `Colossal.Json.DiffUtility+<>c__DisplayClass27_0`  
- `Colossal.Json.DiffUtility+<>c__DisplayClass9_0`  

