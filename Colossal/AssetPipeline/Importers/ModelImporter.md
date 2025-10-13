# Colossal.AssetPipeline.Importers.ModelImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public abstract class ModelImporter : Colossal.AssetPipeline.Importers.IAssetImporter, Colossal.AssetPipeline.Importers.ISettingable
{
    public System.String displayName { get; }

    protected ModelImporter();

    public virtual Colossal.AssetPipeline.IAsset CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
    public abstract Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    public abstract System.Boolean Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String path, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance);
}
```


## Properties

- `public System.String displayName { get }`  

```csharp
public System.String displayName { get; }
```


## Constructors

- `protected ModelImporter()`  

```csharp
protected ModelImporter();
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

- `public abstract Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String path, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance) : System.Boolean`  

```csharp
public abstract System.Boolean Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String path, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance);
```


## Nested types

- `Colossal.AssetPipeline.Importers.ModelImporter+ModelList`  
- `Colossal.AssetPipeline.Importers.ModelImporter+Model`  

