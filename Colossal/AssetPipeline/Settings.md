# Colossal.AssetPipeline.Settings

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Settings
{
    private System.Collections.Generic.List<System.ValueTuple<System.String, System.Collections.Generic.List<System.String>>> m_AssetMappingRegexCache;
    private System.Collections.Generic.List<System.ValueTuple<System.String, System.String, System.String>> m_SharedAssetsRegexCache;
    public System.Collections.Generic.Dictionary<System.String, System.Type> importerTypeHints;
    public System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.ISettings> importSettings;
    public System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.String>> assetMapping;
    public System.Collections.Generic.Dictionary<System.String, System.String> sharedAssets;
    public System.Collections.Generic.List<System.String> ignoreSuffixes;
    public System.String mainAsset;
    public Colossal.AssetPipeline.Pipeline pipeline;
    public System.Boolean useProceduralAnimation;
    private static readonly Colossal.Logging.ILog log;

    public System.Void CacheRegexPatterns();
    private static System.Int32 CalculateScore(System.String regex);
    public static Colossal.AssetPipeline.Settings GetDefault(System.String mainAsset);
    public Colossal.AssetPipeline.Importers.ISettings GetImportSettings(System.String name, Colossal.AssetPipeline.Importers.IAssetImporter importer, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    public T GetImportSettings<T>(System.String name, Colossal.AssetPipeline.Importers.IAssetImporter importer, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    public System.Boolean GetPostProcessSettings(System.String name, Colossal.AssetPipeline.Importers.ISettingable importer, Colossal.AssetPipeline.Diagnostic.ReportBase report, Colossal.AssetPipeline.Importers.ISettings& settings);
    public System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> UsedShaderAssets(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> group, Colossal.AssetPipeline.Diagnostic.Report+Asset report);
}
```


## Fields

- `private System.Collections.Generic.List<System.ValueTuple<System.String, System.Collections.Generic.List<System.String>>> m_AssetMappingRegexCache`  

```csharp
private System.Collections.Generic.List<System.ValueTuple<System.String, System.Collections.Generic.List<System.String>>> m_AssetMappingRegexCache;
```

- `private System.Collections.Generic.List<System.ValueTuple<System.String, System.String, System.String>> m_SharedAssetsRegexCache`  

```csharp
private System.Collections.Generic.List<System.ValueTuple<System.String, System.String, System.String>> m_SharedAssetsRegexCache;
```

- `public System.Collections.Generic.Dictionary<System.String, System.Type> importerTypeHints`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Type> importerTypeHints;
```

- `public System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.ISettings> importSettings`  

```csharp
public System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.ISettings> importSettings;
```

- `public System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.String>> assetMapping`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.String>> assetMapping;
```

- `public System.Collections.Generic.Dictionary<System.String, System.String> sharedAssets`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.String> sharedAssets;
```

- `public System.Collections.Generic.List<System.String> ignoreSuffixes`  

```csharp
public System.Collections.Generic.List<System.String> ignoreSuffixes;
```

- `public System.String mainAsset`  

```csharp
public System.String mainAsset;
```

- `public Colossal.AssetPipeline.Pipeline pipeline`  

```csharp
public Colossal.AssetPipeline.Pipeline pipeline;
```

- `public System.Boolean useProceduralAnimation`  

```csharp
public System.Boolean useProceduralAnimation;
```

- `private static readonly Colossal.Logging.ILog log`  

```csharp
private static readonly Colossal.Logging.ILog log;
```


## Methods

- `public CacheRegexPatterns() : System.Void`  

```csharp
public System.Void CacheRegexPatterns();
```

- `private static CalculateScore(System.String regex) : System.Int32`  

```csharp
private static System.Int32 CalculateScore(System.String regex);
```

- `public static GetDefault(System.String mainAsset) : Colossal.AssetPipeline.Settings`  

```csharp
public static Colossal.AssetPipeline.Settings GetDefault(System.String mainAsset);
```

- `public GetImportSettings(System.String name, Colossal.AssetPipeline.Importers.IAssetImporter importer, Colossal.AssetPipeline.Diagnostic.ReportBase report) : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetImportSettings(System.String name, Colossal.AssetPipeline.Importers.IAssetImporter importer, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `public GetImportSettings<T>(System.String name, Colossal.AssetPipeline.Importers.IAssetImporter importer, Colossal.AssetPipeline.Diagnostic.ReportBase report) : T`  

```csharp
public T GetImportSettings<T>(System.String name, Colossal.AssetPipeline.Importers.IAssetImporter importer, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `public GetPostProcessSettings(System.String name, Colossal.AssetPipeline.Importers.ISettingable importer, Colossal.AssetPipeline.Diagnostic.ReportBase report, Colossal.AssetPipeline.Importers.ISettings& settings) : System.Boolean`  

```csharp
public System.Boolean GetPostProcessSettings(System.String name, Colossal.AssetPipeline.Importers.ISettingable importer, Colossal.AssetPipeline.Diagnostic.ReportBase report, Colossal.AssetPipeline.Importers.ISettings& settings);
```

- `public UsedShaderAssets(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> group, Colossal.AssetPipeline.Diagnostic.Report+Asset report) : System.Collections.Generic.IReadOnlyDictionary<System.String, System.String>`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> UsedShaderAssets(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> group, Colossal.AssetPipeline.Diagnostic.Report+Asset report);
```


## Nested types

- `Colossal.AssetPipeline.Settings+Defaults`  
- `Colossal.AssetPipeline.Settings+<>c`  

