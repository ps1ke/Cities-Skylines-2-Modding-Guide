# Colossal.AssetPipeline.Importers.FBXImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Importers.ModelImporter`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `Extension`  

## Code

```csharp
public class FBXImporter : Colossal.AssetPipeline.Importers.ModelImporter, Colossal.AssetPipeline.Importers.IAssetImporter, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfImport;

    public FBXImporter();

    public virtual Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    public virtual System.Boolean Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance);
    private Colossal.AssetPipeline.Importers.ModelImporter+ModelList Import(Colossal.AssetPipeline.Importers.FBXImporter+ImportSettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
}
```


## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImport`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfImport;
```


## Constructors

- `public FBXImporter()`  

```csharp
public FBXImporter();
```


## Methods

- `public virtual GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public virtual Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `public virtual Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance) : System.Boolean`  

```csharp
public virtual System.Boolean Import<T>(Colossal.AssetPipeline.Importers.ISettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report, T& instance);
```

- `private Import(Colossal.AssetPipeline.Importers.FBXImporter+ImportSettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : Colossal.AssetPipeline.Importers.ModelImporter+ModelList`  

```csharp
private Colossal.AssetPipeline.Importers.ModelImporter+ModelList Import(Colossal.AssetPipeline.Importers.FBXImporter+ImportSettings importSettings, System.String filePath, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```


## Nested types

- `Colossal.AssetPipeline.Importers.FBXImporter+ImportSettings`  

