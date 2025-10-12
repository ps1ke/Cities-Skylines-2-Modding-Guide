# Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfDetectAlphaClip`  

## Properties

- `public System.Int32 priority { get }`  

## Constructors

- `public SurfacePostProcessor()`  

## Methods

- `private ApplySurfaceProperties(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Surface surface) : System.Void`  
- `private DetectModelNeedsAlphaClip(Colossal.AssetPipeline.Diagnostic.Report+ImportStep step, Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture) : System.Boolean`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report) : System.Void`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Pipeline pipeline, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report) : System.Void`  
- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `private GetMaterialTemplate(Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings settings, System.String template) : System.String`  
- `private ReplaceStandardProperties(Colossal.AssetPipeline.Surface surface) : System.Void`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+IncorrectStandardProperties`  
- `Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+DetectModelNeedsAlphaClipShader`  
- `Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+DetectModelNeedsAlphaClipJob`  

