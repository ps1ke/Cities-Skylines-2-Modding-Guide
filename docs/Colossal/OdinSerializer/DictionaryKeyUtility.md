# Colossal.OdinSerializer.DictionaryKeyUtility

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Boolean> GetSupportedDictionaryKeyTypesResults`  
- `private static readonly System.Collections.Generic.HashSet<System.Type> BaseSupportedDictionaryKeyTypes`  
- `private static readonly System.Collections.Generic.HashSet<System.Char> AllowedSpecialKeyStrChars`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.IDictionaryKeyPathProvider> TypeToKeyPathProviders`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, Colossal.OdinSerializer.IDictionaryKeyPathProvider> IDToKeyPathProviders`  
- `private static readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.IDictionaryKeyPathProvider, System.String> ProviderToID`  
- `private static readonly System.Collections.Generic.Dictionary<System.Object, System.String> ObjectsToTempKeys`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Object> TempKeysToObjects`  
- `private static System.Int64 tempKeyCounter`  

## Methods

- `private static FromTo(System.String str, System.Int32 from, System.Int32 to) : System.String`  
- `public static GetDictionaryKeyString(System.Object key) : System.String`  
- `public static GetDictionaryKeyValue(System.String keyStr, System.Type expectedType) : System.Object`  
- `public static GetPersistentPathKeyTypes() : System.Collections.Generic.IEnumerable<System.Type>`  
- `public static KeyTypeSupportsPersistentPaths(System.Type type) : System.Boolean`  
- `private static LogInvalidKeyPathProvider(System.Type type, System.Reflection.Assembly assembly, System.String reason) : System.Void`  
- `private static PrivateIsSupportedDictionaryKeyType(System.Type type) : System.Boolean`  

## Nested types

- `Colossal.OdinSerializer.DictionaryKeyUtility+UnityObjectKeyComparer<T>`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+FallbackKeyComparer<T>`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+KeyComparer<T>`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+<>c`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+<>c__DisplayClass12_0`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+<GetPersistentPathKeyTypes>d__14`  

