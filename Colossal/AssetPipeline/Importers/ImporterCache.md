# Colossal.AssetPipeline.Importers.ImporterCache

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ImporterCache
{
    private static Colossal.Logging.ILog log;
    private static System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.Type>> sSupportedImporters;
    private static System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> sSupportedExtensions;
    private static System.Collections.Concurrent.ConcurrentDictionary<System.Type, Colossal.AssetPipeline.Importers.IAssetImporter> sImportersInstance;

    public static System.Void CacheSupportedExtensions(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
    public static Colossal.AssetPipeline.Importers.IAssetImporter GetImporter(System.String extension, System.Type typeHint);
    public static System.Boolean GetImporter<T>(System.String path, T& importer, System.Collections.Generic.Dictionary<System.String, System.Type> typeHints);
    public static T GetInstance<T>();
    public static Colossal.AssetPipeline.Importers.IAssetImporter GetInstance(System.Type type);
    public static System.Collections.Generic.IEnumerable<System.String> GetSupportedExtensions(System.Type type);
    public static System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.Type>> GetSupportedExtensions();
    private static System.Type GetTopAbstractType(System.Type type);
    public static System.Void Reset();
    public static System.Boolean Supports(System.String extension);
}
```


## Fields

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.Type>> sSupportedImporters`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.Type>> sSupportedImporters;
```

- `private static System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> sSupportedExtensions`  

```csharp
private static System.Collections.Generic.Dictionary<System.Type, System.Collections.Generic.List<System.String>> sSupportedExtensions;
```

- `private static System.Collections.Concurrent.ConcurrentDictionary<System.Type, Colossal.AssetPipeline.Importers.IAssetImporter> sImportersInstance`  

```csharp
private static System.Collections.Concurrent.ConcurrentDictionary<System.Type, Colossal.AssetPipeline.Importers.IAssetImporter> sImportersInstance;
```


## Methods

- `public static CacheSupportedExtensions(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report = null) : System.Void`  

```csharp
public static System.Void CacheSupportedExtensions(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
```

- `public static GetImporter(System.String extension, System.Type typeHint = null) : Colossal.AssetPipeline.Importers.IAssetImporter`  

```csharp
public static Colossal.AssetPipeline.Importers.IAssetImporter GetImporter(System.String extension, System.Type typeHint);
```

- `public static GetImporter<T>(System.String path, T& importer, System.Collections.Generic.Dictionary<System.String, System.Type> typeHints = null) : System.Boolean`  

```csharp
public static System.Boolean GetImporter<T>(System.String path, T& importer, System.Collections.Generic.Dictionary<System.String, System.Type> typeHints);
```

- `public static GetInstance<T>() : T`  

```csharp
public static T GetInstance<T>();
```

- `public static GetInstance(System.Type type) : Colossal.AssetPipeline.Importers.IAssetImporter`  

```csharp
public static Colossal.AssetPipeline.Importers.IAssetImporter GetInstance(System.Type type);
```

- `public static GetSupportedExtensions(System.Type type) : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.String> GetSupportedExtensions(System.Type type);
```

- `public static GetSupportedExtensions() : System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.Type>>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.Type>> GetSupportedExtensions();
```

- `private static GetTopAbstractType(System.Type type) : System.Type`  

```csharp
private static System.Type GetTopAbstractType(System.Type type);
```

- `public static Reset() : System.Void`  

```csharp
public static System.Void Reset();
```

- `public static Supports(System.String extension) : System.Boolean`  

```csharp
public static System.Boolean Supports(System.String extension);
```


## Nested types

- `Colossal.AssetPipeline.Importers.ImporterCache+<>c`  

