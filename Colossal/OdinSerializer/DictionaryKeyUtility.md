# Colossal.OdinSerializer.DictionaryKeyUtility

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class DictionaryKeyUtility
{
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Boolean> GetSupportedDictionaryKeyTypesResults;
    private static readonly System.Collections.Generic.HashSet<System.Type> BaseSupportedDictionaryKeyTypes;
    private static readonly System.Collections.Generic.HashSet<System.Char> AllowedSpecialKeyStrChars;
    private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.IDictionaryKeyPathProvider> TypeToKeyPathProviders;
    private static readonly System.Collections.Generic.Dictionary<System.String, Colossal.OdinSerializer.IDictionaryKeyPathProvider> IDToKeyPathProviders;
    private static readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.IDictionaryKeyPathProvider, System.String> ProviderToID;
    private static readonly System.Collections.Generic.Dictionary<System.Object, System.String> ObjectsToTempKeys;
    private static readonly System.Collections.Generic.Dictionary<System.String, System.Object> TempKeysToObjects;
    private static System.Int64 tempKeyCounter;

    private static System.String FromTo(System.String str, System.Int32 from, System.Int32 to);
    public static System.String GetDictionaryKeyString(System.Object key);
    public static System.Object GetDictionaryKeyValue(System.String keyStr, System.Type expectedType);
    public static System.Collections.Generic.IEnumerable<System.Type> GetPersistentPathKeyTypes();
    public static System.Boolean KeyTypeSupportsPersistentPaths(System.Type type);
    private static System.Void LogInvalidKeyPathProvider(System.Type type, System.Reflection.Assembly assembly, System.String reason);
    private static System.Boolean PrivateIsSupportedDictionaryKeyType(System.Type type);
}
```


## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Boolean> GetSupportedDictionaryKeyTypesResults`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Boolean> GetSupportedDictionaryKeyTypesResults;
```

- `private static readonly System.Collections.Generic.HashSet<System.Type> BaseSupportedDictionaryKeyTypes`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.Type> BaseSupportedDictionaryKeyTypes;
```

- `private static readonly System.Collections.Generic.HashSet<System.Char> AllowedSpecialKeyStrChars`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.Char> AllowedSpecialKeyStrChars;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.IDictionaryKeyPathProvider> TypeToKeyPathProviders`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.IDictionaryKeyPathProvider> TypeToKeyPathProviders;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, Colossal.OdinSerializer.IDictionaryKeyPathProvider> IDToKeyPathProviders`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, Colossal.OdinSerializer.IDictionaryKeyPathProvider> IDToKeyPathProviders;
```

- `private static readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.IDictionaryKeyPathProvider, System.String> ProviderToID`  

```csharp
private static readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.IDictionaryKeyPathProvider, System.String> ProviderToID;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Object, System.String> ObjectsToTempKeys`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Object, System.String> ObjectsToTempKeys;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Object> TempKeysToObjects`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, System.Object> TempKeysToObjects;
```

- `private static System.Int64 tempKeyCounter`  

```csharp
private static System.Int64 tempKeyCounter;
```


## Methods

- `private static FromTo(System.String str, System.Int32 from, System.Int32 to) : System.String`  

```csharp
private static System.String FromTo(System.String str, System.Int32 from, System.Int32 to);
```

- `public static GetDictionaryKeyString(System.Object key) : System.String`  

```csharp
public static System.String GetDictionaryKeyString(System.Object key);
```

- `public static GetDictionaryKeyValue(System.String keyStr, System.Type expectedType) : System.Object`  

```csharp
public static System.Object GetDictionaryKeyValue(System.String keyStr, System.Type expectedType);
```

- `public static GetPersistentPathKeyTypes() : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetPersistentPathKeyTypes();
```

- `public static KeyTypeSupportsPersistentPaths(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean KeyTypeSupportsPersistentPaths(System.Type type);
```

- `private static LogInvalidKeyPathProvider(System.Type type, System.Reflection.Assembly assembly, System.String reason) : System.Void`  

```csharp
private static System.Void LogInvalidKeyPathProvider(System.Type type, System.Reflection.Assembly assembly, System.String reason);
```

- `private static PrivateIsSupportedDictionaryKeyType(System.Type type) : System.Boolean`  

```csharp
private static System.Boolean PrivateIsSupportedDictionaryKeyType(System.Type type);
```


## Nested types

- `Colossal.OdinSerializer.DictionaryKeyUtility+UnityObjectKeyComparer<T>`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+FallbackKeyComparer<T>`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+KeyComparer<T>`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+<>c`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+<>c__DisplayClass12_0`  
- `Colossal.OdinSerializer.DictionaryKeyUtility+<GetPersistentPathKeyTypes>d__14`  

