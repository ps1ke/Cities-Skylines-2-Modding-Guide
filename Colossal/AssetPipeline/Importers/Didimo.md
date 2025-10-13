# Colossal.AssetPipeline.Importers.DidimoImporter+Didimo

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Importers.ModelImporter`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `Extension`  

## Code

```csharp
public class Didimo : Colossal.AssetPipeline.Importers.ModelImporter, Colossal.AssetPipeline.Importers.IAssetImporter, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfImport;

    public Didimo();

    public virtual Colossal.AssetPipeline.IAsset CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
    public virtual Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    public virtual System.Boolean Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance);
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String path, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
    private System.Boolean ValidateHeader(System.IO.BinaryReader reader);
}
```


## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImport`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfImport;
```


## Constructors

- `public Didimo()`  

```csharp
public Didimo();
```


## Methods

- `public virtual CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset) : Colossal.AssetPipeline.IAsset`  

```csharp
public virtual Colossal.AssetPipeline.IAsset CreateAsset(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
```

- `public virtual GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public virtual Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `public virtual Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance) : System.Boolean`  

```csharp
public virtual System.Boolean Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance);
```

- `public Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String path, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData Import(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String path, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```

- `private ValidateHeader(System.IO.BinaryReader reader) : System.Boolean`  

```csharp
private System.Boolean ValidateHeader(System.IO.BinaryReader reader);
```


## Nested types

- `Colossal.AssetPipeline.Importers.DidimoImporter+Didimo+ImportSettings`  

