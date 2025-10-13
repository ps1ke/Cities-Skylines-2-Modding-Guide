# Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public class SurfacePostProcessor : Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfDetectAlphaClip;

    public System.Int32 priority { get; }

    public SurfacePostProcessor();

    private System.Void ApplySurfaceProperties(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Surface surface);
    private System.Boolean DetectModelNeedsAlphaClip(Colossal.AssetPipeline.Diagnostic.Report+ImportStep step, Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Pipeline pipeline, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report);
    public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    private System.String GetMaterialTemplate(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, System.String template);
    private System.Void ReplaceStandardProperties(Colossal.AssetPipeline.Surface surface);
    public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface);
}
```


## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfDetectAlphaClip`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfDetectAlphaClip;
```


## Properties

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```


## Constructors

- `public SurfacePostProcessor()`  

```csharp
public SurfacePostProcessor();
```


## Methods

- `private ApplySurfaceProperties(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Surface surface) : System.Void`  

```csharp
private System.Void ApplySurfaceProperties(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Surface surface);
```

- `private DetectModelNeedsAlphaClip(Colossal.AssetPipeline.Diagnostic.Report+ImportStep step, Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture) : System.Boolean`  

```csharp
private System.Boolean DetectModelNeedsAlphaClip(Colossal.AssetPipeline.Diagnostic.Report+ImportStep step, Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Pipeline pipeline, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Pipeline pipeline, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report);
```

- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `private GetMaterialTemplate(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, System.String template) : System.String`  

```csharp
private System.String GetMaterialTemplate(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, System.String template);
```

- `private ReplaceStandardProperties(Colossal.AssetPipeline.Surface surface) : System.Void`  

```csharp
private System.Void ReplaceStandardProperties(Colossal.AssetPipeline.Surface surface);
```

- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface) : System.Boolean`  

```csharp
public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+IncorrectStandardProperties`  
- `Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+DetectModelNeedsAlphaClipShader`  
- `Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+DetectModelNeedsAlphaClipJob`  

