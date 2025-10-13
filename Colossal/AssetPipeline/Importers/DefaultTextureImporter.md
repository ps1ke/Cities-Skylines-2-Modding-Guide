# Colossal.AssetPipeline.Importers.DefaultTextureImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Importers.TextureImporter`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `Extension`  

## Code

```csharp
public class DefaultTextureImporter : Colossal.AssetPipeline.Importers.TextureImporter, Colossal.AssetPipeline.Importers.IAssetImporter, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfImport;

    public DefaultTextureImporter();

    public virtual Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    public virtual Colossal.AssetPipeline.Importers.TextureImporter+Texture Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
    public Colossal.AssetPipeline.Importers.TextureImporter+Texture Import(Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
}
```


## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImport`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfImport;
```


## Constructors

- `public DefaultTextureImporter()`  

```csharp
public DefaultTextureImporter();
```


## Methods

- `public virtual GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public virtual Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `public virtual Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : Colossal.AssetPipeline.Importers.TextureImporter+Texture`  

```csharp
public virtual Colossal.AssetPipeline.Importers.TextureImporter+Texture Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```

- `public Import(Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report = null) : Colossal.AssetPipeline.Importers.TextureImporter+Texture`  

```csharp
public Colossal.AssetPipeline.Importers.TextureImporter+Texture Import(Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```


## Nested types

- `Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings`  

