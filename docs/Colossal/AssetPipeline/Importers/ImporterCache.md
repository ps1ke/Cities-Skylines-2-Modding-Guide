# Colossal.AssetPipeline.Importers.ImporterCache

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static Colossal.Logging.ILog log`  
- `private static System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.Type>> sSupportedImporters`  
- `private static System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> sSupportedExtensions`  
- `private static System.Collections.Concurrent.ConcurrentDictionary<System.Type, Colossal.AssetPipeline.Importers.IAssetImporter> sImportersInstance`  

## Methods

- `public static CacheSupportedExtensions(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report = null) : System.Void`  
- `public static GetImporter(System.String extension, System.Type typeHint = null) : Colossal.AssetPipeline.Importers.IAssetImporter`  
- `public static GetImporter<T>(System.String path, T& importer, System.Collections.Generic.Dictionary<System.String, System.Type> typeHints = null) : System.Boolean`  
- `public static GetInstance<T>() : T`  
- `public static GetInstance(System.Type type) : Colossal.AssetPipeline.Importers.IAssetImporter`  
- `public static GetSupportedExtensions(System.Type type) : System.Collections.Generic.IEnumerable<System.String>`  
- `public static GetSupportedExtensions() : System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.Type>>`  
- `private static GetTopAbstractType(System.Type type) : System.Type`  
- `public static Reset() : System.Void`  
- `public static Supports(System.String extension) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.Importers.ImporterCache+<>c`  

