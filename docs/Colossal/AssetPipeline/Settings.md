# Colossal.AssetPipeline.Settings

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private System.Collections.Generic.List<System.ValueTuple<System.String, System.Collections.Generic.List<System.String>>> m_AssetMappingRegexCache`  
- `private System.Collections.Generic.List<System.ValueTuple<System.String, System.String, System.String>> m_SharedAssetsRegexCache`  
- `public System.Collections.Generic.Dictionary<System.String, System.Type> importerTypeHints`  
- `public System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.ISettings> importSettings`  
- `public System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<System.String>> assetMapping`  
- `public System.Collections.Generic.Dictionary<System.String, System.String> sharedAssets`  
- `public System.Collections.Generic.List<System.String> ignoreSuffixes`  
- `public System.String mainAsset`  
- `public Colossal.AssetPipeline.Pipeline pipeline`  
- `public System.Boolean useProceduralAnimation`  
- `private static readonly Colossal.Logging.ILog log`  

## Methods

- `public CacheRegexPatterns() : System.Void`  
- `private static CalculateScore(System.String regex) : System.Int32`  
- `public static GetDefault(System.String mainAsset) : Colossal.AssetPipeline.Settings`  
- `public GetImportSettings(System.String name, Colossal.AssetPipeline.Importers.IAssetImporter importer, Colossal.AssetPipeline.Diagnostic.ReportBase report) : Colossal.AssetPipeline.Importers.ISettings`  
- `public GetImportSettings<T>(System.String name, Colossal.AssetPipeline.Importers.IAssetImporter importer, Colossal.AssetPipeline.Diagnostic.ReportBase report) : T`  
- `public GetPostProcessSettings(System.String name, Colossal.AssetPipeline.Importers.ISettingable importer, Colossal.AssetPipeline.Diagnostic.ReportBase report, Colossal.AssetPipeline.Importers.ISettings& settings) : System.Boolean`  
- `public UsedShaderAssets(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> group, Colossal.AssetPipeline.Diagnostic.Report+Asset report) : System.Collections.Generic.IReadOnlyDictionary<System.String, System.String>`  

## Nested types

- `Colossal.AssetPipeline.Settings+Defaults`  
- `Colossal.AssetPipeline.Settings+<>c`  

