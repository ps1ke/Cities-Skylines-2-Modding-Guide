# Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveBakingPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public class EmissiveBakingPostProcessor : Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;
    private static Unity.Profiling.ProfilerMarker s_ProfScanLights;
    private static Unity.Profiling.ProfilerMarker s_Stencil;
    private static Unity.Profiling.ProfilerMarker s_Gather;
    private static Unity.Profiling.ProfilerMarker s_Complex;
    private static Unity.Profiling.ProfilerMarker s_Resolve;
    private static Unity.Profiling.ProfilerMarker s_Final;

    public System.Int32 priority { get; }

    public EmissiveBakingPostProcessor();

    private static System.Boolean CollectBakingData(Colossal.AssetPipeline.Surface surface, System.Collections.Generic.IEnumerable<System.String> maps, System.Int32& width, System.Int32& height, UnityEngine.Experimental.Rendering.GraphicsFormat& format, System.Collections.Generic.List`1[[Colossal.AssetPipeline.Importers.TextureImporter+Texture, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& emissiveColors, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    private static System.Boolean CollectBakingData(Colossal.AssetPipeline.Surface surface, System.Int32& width, System.Int32& height, UnityEngine.Experimental.Rendering.GraphicsFormat& format, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures& textures, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report);
    public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    private static System.Void RenderEmissivesTriangles(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveLayers layerInfo, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup> groups, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList, Unity.Collections.NativeArray<UnityEngine.Color32> vertexLightIds, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source, System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.Byte> rasterTarget, System.Boolean& isShared);
    private static Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveLayers ScanLights(System.Int32 width, System.Int32 height, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source);
    public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface);
    private static UnityEngine.Color UpdateEmissiveMap(UnityEngine.Color inColor, UnityEngine.Color currentColor, System.Int32 channel, System.Single lightLuminance);
}
```


## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;
```

- `private static Unity.Profiling.ProfilerMarker s_ProfScanLights`  

```csharp
private static Unity.Profiling.ProfilerMarker s_ProfScanLights;
```

- `private static Unity.Profiling.ProfilerMarker s_Stencil`  

```csharp
private static Unity.Profiling.ProfilerMarker s_Stencil;
```

- `private static Unity.Profiling.ProfilerMarker s_Gather`  

```csharp
private static Unity.Profiling.ProfilerMarker s_Gather;
```

- `private static Unity.Profiling.ProfilerMarker s_Complex`  

```csharp
private static Unity.Profiling.ProfilerMarker s_Complex;
```

- `private static Unity.Profiling.ProfilerMarker s_Resolve`  

```csharp
private static Unity.Profiling.ProfilerMarker s_Resolve;
```

- `private static Unity.Profiling.ProfilerMarker s_Final`  

```csharp
private static Unity.Profiling.ProfilerMarker s_Final;
```


## Properties

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```


## Constructors

- `public EmissiveBakingPostProcessor()`  

```csharp
public EmissiveBakingPostProcessor();
```


## Methods

- `private static CollectBakingData(Colossal.AssetPipeline.Surface surface, System.Collections.Generic.IEnumerable<System.String> maps, System.Int32& width, System.Int32& height, UnityEngine.Experimental.Rendering.GraphicsFormat& format, System.Collections.Generic.List`1[[Colossal.AssetPipeline.Importers.TextureImporter+Texture, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& emissiveColors, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
private static System.Boolean CollectBakingData(Colossal.AssetPipeline.Surface surface, System.Collections.Generic.IEnumerable<System.String> maps, System.Int32& width, System.Int32& height, UnityEngine.Experimental.Rendering.GraphicsFormat& format, System.Collections.Generic.List`1[[Colossal.AssetPipeline.Importers.TextureImporter+Texture, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& emissiveColors, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `private static CollectBakingData(Colossal.AssetPipeline.Surface surface, System.Int32& width, System.Int32& height, UnityEngine.Experimental.Rendering.GraphicsFormat& format, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures& textures, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
private static System.Boolean CollectBakingData(Colossal.AssetPipeline.Surface surface, System.Int32& width, System.Int32& height, UnityEngine.Experimental.Rendering.GraphicsFormat& format, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures& textures, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report);
```

- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `private static RenderEmissivesTriangles(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveLayers layerInfo, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup> groups, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList, Unity.Collections.NativeArray<UnityEngine.Color32> vertexLightIds, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source, System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.Byte> rasterTarget, System.Boolean& isShared) : System.Void`  

```csharp
private static System.Void RenderEmissivesTriangles(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveLayers layerInfo, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup> groups, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList, Unity.Collections.NativeArray<UnityEngine.Color32> vertexLightIds, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source, System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.Byte> rasterTarget, System.Boolean& isShared);
```

- `private static ScanLights(System.Int32 width, System.Int32 height, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source) : Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveLayers`  

```csharp
private static Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveLayers ScanLights(System.Int32 width, System.Int32 height, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source);
```

- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface) : System.Boolean`  

```csharp
public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface);
```

- `private static UpdateEmissiveMap(UnityEngine.Color inColor, UnityEngine.Color currentColor, System.Int32 channel, System.Single lightLuminance) : UnityEngine.Color`  

```csharp
private static UnityEngine.Color UpdateEmissiveMap(UnityEngine.Color inColor, UnityEngine.Color currentColor, System.Int32 channel, System.Single lightLuminance);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveBakingPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveBakingPostProcessor+<>c`  

