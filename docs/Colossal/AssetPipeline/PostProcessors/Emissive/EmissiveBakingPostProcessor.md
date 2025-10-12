# Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveBakingPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  
- `private static Unity.Profiling.ProfilerMarker s_ProfScanLights`  
- `private static Unity.Profiling.ProfilerMarker s_Stencil`  
- `private static Unity.Profiling.ProfilerMarker s_Gather`  
- `private static Unity.Profiling.ProfilerMarker s_Complex`  
- `private static Unity.Profiling.ProfilerMarker s_Resolve`  
- `private static Unity.Profiling.ProfilerMarker s_Final`  

## Properties

- `public System.Int32 priority { get }`  

## Constructors

- `public EmissiveBakingPostProcessor()`  

## Methods

- `private static CollectBakingData(Colossal.AssetPipeline.Surface surface, System.Collections.Generic.IEnumerable<System.String> maps, System.Int32& width, System.Int32& height, UnityEngine.Experimental.Rendering.GraphicsFormat& format, System.Collections.Generic.List`1[[Colossal.AssetPipeline.Importers.TextureImporter+Texture, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& emissiveColors, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `private static CollectBakingData(Colossal.AssetPipeline.Surface surface, System.Int32& width, System.Int32& height, UnityEngine.Experimental.Rendering.GraphicsFormat& format, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures& textures, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report) : System.Void`  
- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `private static RenderEmissivesTriangles(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveLayers layerInfo, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup> groups, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList, Unity.Collections.NativeArray<UnityEngine.Color32> vertexLightIds, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source, System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.Byte> rasterTarget, System.Boolean& isShared) : System.Void`  
- `private static ScanLights(System.Int32 width, System.Int32 height, Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source) : Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveLayers`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface) : System.Boolean`  
- `private static UpdateEmissiveMap(UnityEngine.Color inColor, UnityEngine.Color currentColor, System.Int32 channel, System.Single lightLuminance) : UnityEngine.Color`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveBakingPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveBakingPostProcessor+<>c`  

