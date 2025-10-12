# Colossal.AssetPipeline.Importers.ModelImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Properties

- `public System.String displayName { get }`  

## Constructors

- `protected ModelImporter()`  

## Methods

- `public virtual CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset) : Colossal.AssetPipeline.IAsset`  
- `public abstract GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `public abstract Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String path, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.Importers.ModelImporter+ModelList`  
- `Colossal.AssetPipeline.Importers.ModelImporter+Model`  

