# Colossal.AssetPipeline.Importers.DidimoImporter+Didimo

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Importers.ModelImporter`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `Extension`  

## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImport`  

## Constructors

- `public Didimo()`  

## Methods

- `public virtual CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset) : Colossal.AssetPipeline.IAsset`  
- `public virtual GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `public virtual Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance) : System.Boolean`  
- `public Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String path, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData`  
- `private ValidateHeader(System.IO.BinaryReader reader) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.Importers.DidimoImporter+Didimo+ImportSettings`  

