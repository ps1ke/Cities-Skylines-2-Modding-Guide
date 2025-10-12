# Colossal.IO.AssetDatabase.DefaultAssetFactory

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetFactory`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<System.Type, Colossal.IO.AssetDatabase.AddAssetFile> m_TypeFactory`  
- `private readonly System.Collections.Generic.Dictionary<System.String, System.Type> m_ExtensionToTypeMap`  
- `private readonly System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> m_TypeToExtensionMap`  
- `private readonly System.Collections.Generic.HashSet<System.String> m_PriorityExtensions`  
- `private readonly System.Collections.Generic.HashSet<System.Type> m_NonAddressableTypes`  
- `private readonly Colossal.IO.AssetDatabase.DefaultAssetFactory+TypeCompatibilityCache m_TypeCompatibilityCache`  
- `private Colossal.IO.AssetDatabase.COCParser m_COCParser`  
- `private static Colossal.Logging.ILog log`  
- `private static Colossal.IO.AssetDatabase.IAssetFactory s_Instance`  

## Properties

- `public static Colossal.IO.AssetDatabase.IAssetFactory instance { get }`  

## Constructors

- `private DefaultAssetFactory()`  

## Methods

- `internal static <AddSupportedType>g__GetTypename|34_0<T>(Colossal.IO.AssetDatabase.AddAssetFile method) : System.String`  
- `public AddSupportedType<T>(System.String extension, System.Func<T> func, System.Boolean priorityExtension = False, System.Boolean isAddressable = True) : System.Void`  
- `public AddSupportedType<T>(System.String[] extensions, System.Func<T> func, System.Boolean priorityExtension = False, System.Boolean isAddressable = True) : System.Void`  
- `public AddSupportedType<T>(Colossal.IO.AssetDatabase.AddAssetFile createCallback, System.Boolean isAddressable = True) : System.Void`  
- `public CreateAndRegisterAsset<T>(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db) : T`  
- `public static CreateAsset<T>(System.Func<T> constructor) : Colossal.IO.AssetDatabase.AddAssetFile`  
- `public static CreateAsset(System.Type type) : Colossal.IO.AssetDatabase.AddAssetFile`  
- `internal CreateSettingAssets(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db) : Colossal.IO.AssetDatabase.SettingAsset`  
- `public GetAssetMimes<T>(System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes) : System.Boolean`  
- `public GetAssetMimes(System.Type type, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes) : System.Boolean`  
- `public GetAssetType(System.String mime, System.Type& type) : System.Boolean`  
- `public GetSupportedAssetTypes() : System.Collections.Generic.IReadOnlyCollection<System.Type>`  
- `public GetSupportedExtensions() : System.Collections.Generic.IReadOnlyCollection<System.String>`  
- `public GetSupportedExtensions(System.Boolean priorityData) : System.Collections.Generic.IReadOnlyCollection<System.String>`  
- `public IsAddressable(System.Type type) : System.Boolean`  
- `public IsAssignable(System.Type baseType, System.Type derivedType) : System.Boolean`  
- `private IsPlatformRelevant(System.String fileName) : System.Boolean`  
- `public MapSupportedExtension<T>(System.String[] extensions, System.Boolean priorityExtension = False) : System.Void`  
- `public MapSupportedExtension<T>(System.String extension, System.Boolean priorityExtension = False) : System.Void`  
- `private ReadAllText(System.IO.Stream stream) : System.String`  
- `private RegisterSupportedTypes() : System.Void`  
- `public RemoveSupportedType<T>() : System.Void`  
- `public RemoveSupportedType(System.Type type) : System.Void`  
- `private static TryGetPlatform(System.String fileName, Colossal.Platform& platform) : System.Boolean`  
- `public UnmapSupportedExtension(System.String extension) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.DefaultAssetFactory+TypeCompatibilityCache`  
- `Colossal.IO.AssetDatabase.DefaultAssetFactory+<>c`  
- `Colossal.IO.AssetDatabase.DefaultAssetFactory+<>c__DisplayClass21_0<T>`  
- `Colossal.IO.AssetDatabase.DefaultAssetFactory+<>c__DisplayClass22_0`  

