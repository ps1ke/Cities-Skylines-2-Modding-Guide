# Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Impostors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public class ImpostorPostProcessor : Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;

    public System.Int32 priority { get; }

    public ImpostorPostProcessor();

    public static Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets Create(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials bakeMaterials, UnityEngine.GameObject rootGameObject, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings bakingSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Quaternion rotate, System.Action<UnityEngine.Texture> onDebugOutputTexture);
    private Colossal.AssetPipeline.Importers.ModelImporter+Model CreateModel(System.String name, UnityEngine.Mesh mesh, UnityEngine.Bounds bounds);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, System.String assetRootPath, System.Action<UnityEngine.Texture> onDebugOutputTexture, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPipelineAsset pipeline, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
    private System.Void Execute_MainThread(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
    public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    private Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPipelineAsset GetPipelineAssetFor(System.String rootPath);
    public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset);
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

- `public ImpostorPostProcessor()`  

```csharp
public ImpostorPostProcessor();
```


## Methods

- `public static Create(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials bakeMaterials, UnityEngine.GameObject rootGameObject, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings bakingSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Quaternion rotate, System.Action<UnityEngine.Texture> onDebugOutputTexture = null) : Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets`  

```csharp
public static Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets Create(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials bakeMaterials, UnityEngine.GameObject rootGameObject, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings bakingSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Quaternion rotate, System.Action<UnityEngine.Texture> onDebugOutputTexture);
```

- `private CreateModel(System.String name, UnityEngine.Mesh mesh, UnityEngine.Bounds bounds) : Colossal.AssetPipeline.Importers.ModelImporter+Model`  

```csharp
private Colossal.AssetPipeline.Importers.ModelImporter+Model CreateModel(System.String name, UnityEngine.Mesh mesh, UnityEngine.Bounds bounds);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, System.String assetRootPath, System.Action<UnityEngine.Texture> onDebugOutputTexture, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPipelineAsset pipeline, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, System.String assetRootPath, System.Action<UnityEngine.Texture> onDebugOutputTexture, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPipelineAsset pipeline, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
```

- `private Execute_MainThread(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  

```csharp
private System.Void Execute_MainThread(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
```

- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `private GetPipelineAssetFor(System.String rootPath) : Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPipelineAsset`  

```csharp
private Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPipelineAsset GetPipelineAssetFor(System.String rootPath);
```

- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset) : System.Boolean`  

```csharp
public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+<>c__DisplayClass6_0`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+<>c__DisplayClass7_0`  

