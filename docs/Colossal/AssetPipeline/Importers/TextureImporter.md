# Colossal.AssetPipeline.Importers.TextureImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `BurstCompile`  

## Fields

- `public static System.Int32 overrideCompressionEffort`  

## Properties

- `public System.String displayName { get }`  

## Constructors

- `protected TextureImporter()`  

## Methods

- `public virtual CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset) : Colossal.AssetPipeline.IAsset`  
- `public abstract GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `public abstract Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : Colossal.AssetPipeline.Importers.TextureImporter+Texture`  

## Nested types

- `Colossal.AssetPipeline.Importers.TextureImporter+ITexture`  
- `Colossal.AssetPipeline.Importers.TextureImporter+TextureArray`  
- `Colossal.AssetPipeline.Importers.TextureImporter+Texture`  

