# Colossal.IO.AssetDatabase.DefaultAssetFactory

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetFactory`  

## Code

```csharp
public class DefaultAssetFactory : Colossal.IO.AssetDatabase.IAssetFactory
{
    private readonly System.Collections.Generic.Dictionary<System.Type, Colossal.IO.AssetDatabase.AddAssetFile> m_TypeFactory;
    private readonly System.Collections.Generic.Dictionary<System.String, System.Type> m_ExtensionToTypeMap;
    private readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> m_TypeToExtensionMap;
    private readonly System.Collections.Generic.HashSet<System.String> m_PriorityExtensions;
    private readonly System.Collections.Generic.HashSet<System.Type> m_NonAddressableTypes;
    private readonly Colossal.IO.AssetDatabase.DefaultAssetFactory+TypeCompatibilityCache m_TypeCompatibilityCache;
    private Colossal.IO.AssetDatabase.COCParser m_COCParser;
    private static Colossal.Logging.ILog log;
    private static Colossal.IO.AssetDatabase.IAssetFactory s_Instance;

    public static Colossal.IO.AssetDatabase.IAssetFactory instance { get; }

    private DefaultAssetFactory();

    internal static System.String <AddSupportedType>g__GetTypename|34_0<T>(Colossal.IO.AssetDatabase.AddAssetFile method);
    public System.Void AddSupportedType<T>(System.String extension, System.Func<T> func, System.Boolean priorityExtension, System.Boolean isAddressable);
    public System.Void AddSupportedType<T>(System.String[] extensions, System.Func<T> func, System.Boolean priorityExtension, System.Boolean isAddressable);
    public System.Void AddSupportedType<T>(Colossal.IO.AssetDatabase.AddAssetFile createCallback, System.Boolean isAddressable);
    public T CreateAndRegisterAsset<T>(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db);
    public static Colossal.IO.AssetDatabase.AddAssetFile CreateAsset<T>(System.Func<T> constructor);
    public static Colossal.IO.AssetDatabase.AddAssetFile CreateAsset(System.Type type);
    internal Colossal.IO.AssetDatabase.SettingAsset CreateSettingAssets(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db);
    public System.Boolean GetAssetMimes<T>(System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes);
    public System.Boolean GetAssetMimes(System.Type type, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes);
    public System.Boolean GetAssetType(System.String mime, System.Type& type);
    public System.Collections.Generic.IReadOnlyCollection<System.Type> GetSupportedAssetTypes();
    public System.Collections.Generic.IReadOnlyCollection<System.String> GetSupportedExtensions();
    public System.Collections.Generic.IReadOnlyCollection<System.String> GetSupportedExtensions(System.Boolean priorityData);
    public System.Boolean IsAddressable(System.Type type);
    public System.Boolean IsAssignable(System.Type baseType, System.Type derivedType);
    private System.Boolean IsPlatformRelevant(System.String fileName);
    public System.Void MapSupportedExtension<T>(System.String[] extensions, System.Boolean priorityExtension);
    public System.Void MapSupportedExtension<T>(System.String extension, System.Boolean priorityExtension);
    private System.String ReadAllText(System.IO.Stream stream);
    private System.Void RegisterSupportedTypes();
    public System.Void RemoveSupportedType<T>();
    public System.Void RemoveSupportedType(System.Type type);
    private static System.Boolean TryGetPlatform(System.String fileName, Colossal.Platform& platform);
    public System.Void UnmapSupportedExtension(System.String extension);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<System.Type, Colossal.IO.AssetDatabase.AddAssetFile> m_TypeFactory`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Type, Colossal.IO.AssetDatabase.AddAssetFile> m_TypeFactory;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Type> m_ExtensionToTypeMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Type> m_ExtensionToTypeMap;
```

- `private readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> m_TypeToExtensionMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> m_TypeToExtensionMap;
```

- `private readonly System.Collections.Generic.HashSet<System.String> m_PriorityExtensions`  

```csharp
private readonly System.Collections.Generic.HashSet<System.String> m_PriorityExtensions;
```

- `private readonly System.Collections.Generic.HashSet<System.Type> m_NonAddressableTypes`  

```csharp
private readonly System.Collections.Generic.HashSet<System.Type> m_NonAddressableTypes;
```

- `private readonly Colossal.IO.AssetDatabase.DefaultAssetFactory+TypeCompatibilityCache m_TypeCompatibilityCache`  

```csharp
private readonly Colossal.IO.AssetDatabase.DefaultAssetFactory+TypeCompatibilityCache m_TypeCompatibilityCache;
```

- `private Colossal.IO.AssetDatabase.COCParser m_COCParser`  

```csharp
private Colossal.IO.AssetDatabase.COCParser m_COCParser;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static Colossal.IO.AssetDatabase.IAssetFactory s_Instance`  

```csharp
private static Colossal.IO.AssetDatabase.IAssetFactory s_Instance;
```


## Properties

- `public static Colossal.IO.AssetDatabase.IAssetFactory instance { get }`  

```csharp
public static Colossal.IO.AssetDatabase.IAssetFactory instance { get; }
```


## Constructors

- `private DefaultAssetFactory()`  

```csharp
private DefaultAssetFactory();
```


## Methods

- `internal static <AddSupportedType>g__GetTypename|34_0<T>(Colossal.IO.AssetDatabase.AddAssetFile method) : System.String`  

```csharp
internal static System.String <AddSupportedType>g__GetTypename|34_0<T>(Colossal.IO.AssetDatabase.AddAssetFile method);
```

- `public AddSupportedType<T>(System.String extension, System.Func<T> func, System.Boolean priorityExtension = False, System.Boolean isAddressable = True) : System.Void`  

```csharp
public System.Void AddSupportedType<T>(System.String extension, System.Func<T> func, System.Boolean priorityExtension, System.Boolean isAddressable);
```

- `public AddSupportedType<T>(System.String[] extensions, System.Func<T> func, System.Boolean priorityExtension = False, System.Boolean isAddressable = True) : System.Void`  

```csharp
public System.Void AddSupportedType<T>(System.String[] extensions, System.Func<T> func, System.Boolean priorityExtension, System.Boolean isAddressable);
```

- `public AddSupportedType<T>(Colossal.IO.AssetDatabase.AddAssetFile createCallback, System.Boolean isAddressable = True) : System.Void`  

```csharp
public System.Void AddSupportedType<T>(Colossal.IO.AssetDatabase.AddAssetFile createCallback, System.Boolean isAddressable);
```

- `public CreateAndRegisterAsset<T>(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db) : T`  

```csharp
public T CreateAndRegisterAsset<T>(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `public static CreateAsset<T>(System.Func<T> constructor) : Colossal.IO.AssetDatabase.AddAssetFile`  

```csharp
public static Colossal.IO.AssetDatabase.AddAssetFile CreateAsset<T>(System.Func<T> constructor);
```

- `public static CreateAsset(System.Type type) : Colossal.IO.AssetDatabase.AddAssetFile`  

```csharp
public static Colossal.IO.AssetDatabase.AddAssetFile CreateAsset(System.Type type);
```

- `internal CreateSettingAssets(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db) : Colossal.IO.AssetDatabase.SettingAsset`  

```csharp
internal Colossal.IO.AssetDatabase.SettingAsset CreateSettingAssets(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `public GetAssetMimes<T>(System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes) : System.Boolean`  

```csharp
public System.Boolean GetAssetMimes<T>(System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes);
```

- `public GetAssetMimes(System.Type type, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes) : System.Boolean`  

```csharp
public System.Boolean GetAssetMimes(System.Type type, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes);
```

- `public GetAssetType(System.String mime, System.Type& type) : System.Boolean`  

```csharp
public System.Boolean GetAssetType(System.String mime, System.Type& type);
```

- `public GetSupportedAssetTypes() : System.Collections.Generic.IReadOnlyCollection<System.Type>`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<System.Type> GetSupportedAssetTypes();
```

- `public GetSupportedExtensions() : System.Collections.Generic.IReadOnlyCollection<System.String>`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<System.String> GetSupportedExtensions();
```

- `public GetSupportedExtensions(System.Boolean priorityData) : System.Collections.Generic.IReadOnlyCollection<System.String>`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<System.String> GetSupportedExtensions(System.Boolean priorityData);
```

- `public IsAddressable(System.Type type) : System.Boolean`  

```csharp
public System.Boolean IsAddressable(System.Type type);
```

- `public IsAssignable(System.Type baseType, System.Type derivedType) : System.Boolean`  

```csharp
public System.Boolean IsAssignable(System.Type baseType, System.Type derivedType);
```

- `private IsPlatformRelevant(System.String fileName) : System.Boolean`  

```csharp
private System.Boolean IsPlatformRelevant(System.String fileName);
```

- `public MapSupportedExtension<T>(System.String[] extensions, System.Boolean priorityExtension = False) : System.Void`  

```csharp
public System.Void MapSupportedExtension<T>(System.String[] extensions, System.Boolean priorityExtension);
```

- `public MapSupportedExtension<T>(System.String extension, System.Boolean priorityExtension = False) : System.Void`  

```csharp
public System.Void MapSupportedExtension<T>(System.String extension, System.Boolean priorityExtension);
```

- `private ReadAllText(System.IO.Stream stream) : System.String`  

```csharp
private System.String ReadAllText(System.IO.Stream stream);
```

- `private RegisterSupportedTypes() : System.Void`  

```csharp
private System.Void RegisterSupportedTypes();
```

- `public RemoveSupportedType<T>() : System.Void`  

```csharp
public System.Void RemoveSupportedType<T>();
```

- `public RemoveSupportedType(System.Type type) : System.Void`  

```csharp
public System.Void RemoveSupportedType(System.Type type);
```

- `private static TryGetPlatform(System.String fileName, Colossal.Platform& platform) : System.Boolean`  

```csharp
private static System.Boolean TryGetPlatform(System.String fileName, Colossal.Platform& platform);
```

- `public UnmapSupportedExtension(System.String extension) : System.Void`  

```csharp
public System.Void UnmapSupportedExtension(System.String extension);
```


## Nested types

- `Colossal.IO.AssetDatabase.DefaultAssetFactory+TypeCompatibilityCache`  
- `Colossal.IO.AssetDatabase.DefaultAssetFactory+<>c`  
- `Colossal.IO.AssetDatabase.DefaultAssetFactory+<>c__DisplayClass21_0<T>`  
- `Colossal.IO.AssetDatabase.DefaultAssetFactory+<>c__DisplayClass22_0`  

