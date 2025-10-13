# Colossal.AssetPipeline.Importers.IAssetImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** interface abstract public  

**Implements:** `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public abstract interface IAssetImporter : Colossal.AssetPipeline.Importers.ISettingable
{
    public System.String displayName { get; }

    public abstract Colossal.AssetPipeline.IAsset CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
}
```


## Properties

- `public System.String displayName { get }`  

```csharp
public System.String displayName { get; }
```


## Methods

- `public abstract CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset) : Colossal.AssetPipeline.IAsset`  

```csharp
public abstract Colossal.AssetPipeline.IAsset CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
```


