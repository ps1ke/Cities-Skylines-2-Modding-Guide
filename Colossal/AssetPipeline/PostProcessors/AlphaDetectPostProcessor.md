# Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public class AlphaDetectPostProcessor : Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;

    public System.Int32 priority { get; }

    public AlphaDetectPostProcessor();

    private static System.Boolean ContainsAlpha(Colossal.AssetPipeline.TextureAsset texture);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.TextureAsset texture, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.TextureAsset texture, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
    public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.TextureAsset texture);
}
```


## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;
```


## Properties

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```


## Constructors

- `public AlphaDetectPostProcessor()`  

```csharp
public AlphaDetectPostProcessor();
```


## Methods

- `private static ContainsAlpha(Colossal.AssetPipeline.TextureAsset texture) : System.Boolean`  

```csharp
private static System.Boolean ContainsAlpha(Colossal.AssetPipeline.TextureAsset texture);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.TextureAsset texture, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.TextureAsset texture, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.TextureAsset texture, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.TextureAsset texture, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```

- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.TextureAsset texture) : System.Boolean`  

```csharp
public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.TextureAsset texture);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+AlphaDetectJob8`  
- `Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+AlphaDetectJob16`  

