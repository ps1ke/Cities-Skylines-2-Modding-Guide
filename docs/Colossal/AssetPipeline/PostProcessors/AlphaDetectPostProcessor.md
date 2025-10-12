# Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  

## Properties

- `public System.Int32 priority { get }`  

## Constructors

- `public AlphaDetectPostProcessor()`  

## Methods

- `private static ContainsAlpha(Colossal.AssetPipeline.TextureAsset texture) : System.Boolean`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.TextureAsset texture, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.TextureAsset texture, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  
- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.TextureAsset texture) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+AlphaDetectJob8`  
- `Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+AlphaDetectJob16`  

