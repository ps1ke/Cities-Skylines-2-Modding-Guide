# Colossal.AssetPipeline.Importers.TextureImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public abstract class TextureImporter : Colossal.AssetPipeline.Importers.IAssetImporter, Colossal.AssetPipeline.Importers.ISettingable
{
    public static System.Int32 overrideCompressionEffort;

    public System.String displayName { get; }

    protected TextureImporter();

    public virtual Colossal.AssetPipeline.IAsset CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
    public abstract Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    public abstract Colossal.AssetPipeline.Importers.TextureImporter+Texture Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
}
```


## Fields

- `public static System.Int32 overrideCompressionEffort`  

```csharp
public static System.Int32 overrideCompressionEffort;
```


## Properties

- `public System.String displayName { get }`  

```csharp
public System.String displayName { get; }
```


## Constructors

- `protected TextureImporter()`  

```csharp
protected TextureImporter();
```


## Methods

- `public virtual CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset) : Colossal.AssetPipeline.IAsset`  

```csharp
public virtual Colossal.AssetPipeline.IAsset CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
```

- `public abstract GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public abstract Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `public abstract Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : Colossal.AssetPipeline.Importers.TextureImporter+Texture`  

```csharp
public abstract Colossal.AssetPipeline.Importers.TextureImporter+Texture Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```


## Nested types

- `Colossal.AssetPipeline.Importers.TextureImporter+ITexture`  
- `Colossal.AssetPipeline.Importers.TextureImporter+TextureArray`  
- `Colossal.AssetPipeline.Importers.TextureImporter+Texture`  

