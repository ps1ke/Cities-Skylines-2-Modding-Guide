# Colossal.AssetPipeline.TextureAsset

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Asset<Colossal.AssetPipeline.Importers.TextureImporter, Colossal.AssetPipeline.Importers.TextureImporter+Texture>`  
**Implements:** `Colossal.AssetPipeline.IAsset`, `System.IEquatable<Colossal.AssetPipeline.IAsset>`  

## Code

```csharp
public class TextureAsset : Colossal.AssetPipeline.Asset<Colossal.AssetPipeline.Importers.TextureImporter, Colossal.AssetPipeline.Importers.TextureImporter+Texture>, Colossal.AssetPipeline.IAsset, System.IEquatable<Colossal.AssetPipeline.IAsset>
{
    public System.Boolean hasAlpha { get; set; }

    public TextureAsset(System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset, Colossal.AssetPipeline.Importers.TextureImporter importer, System.Boolean validateFileName);

    public static Colossal.AssetPipeline.TextureAsset CreateDummy(System.String name, System.String dummyPath, System.Boolean validateFileName);
}
```


## Properties

- `public System.Boolean hasAlpha { get; set }`  

```csharp
public System.Boolean hasAlpha { get; set; }
```


## Constructors

- `public TextureAsset(System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset, Colossal.AssetPipeline.Importers.TextureImporter importer, System.Boolean validateFileName)`  

```csharp
public TextureAsset(System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset, Colossal.AssetPipeline.Importers.TextureImporter importer, System.Boolean validateFileName);
```


## Methods

- `public static CreateDummy(System.String name, System.String dummyPath, System.Boolean validateFileName) : Colossal.AssetPipeline.TextureAsset`  

```csharp
public static Colossal.AssetPipeline.TextureAsset CreateDummy(System.String name, System.String dummyPath, System.Boolean validateFileName);
```


