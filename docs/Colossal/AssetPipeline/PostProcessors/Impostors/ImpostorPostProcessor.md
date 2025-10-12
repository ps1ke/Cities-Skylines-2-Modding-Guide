# Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Impostors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  

## Properties

- `public System.Int32 priority { get }`  

## Constructors

- `public ImpostorPostProcessor()`  

## Methods

- `public static Create(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials bakeMaterials, UnityEngine.GameObject rootGameObject, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings bakingSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Quaternion rotate, System.Action<UnityEngine.Texture> onDebugOutputTexture = null) : Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets`  
- `private CreateModel(System.String name, UnityEngine.Mesh mesh, UnityEngine.Bounds bounds) : Colossal.AssetPipeline.Importers.ModelImporter+Model`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, System.String assetRootPath, System.Action<UnityEngine.Texture> onDebugOutputTexture, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPipelineAsset pipeline, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `private Execute_MainThread(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `private GetPipelineAssetFor(System.String rootPath) : Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPipelineAsset`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+<>c__DisplayClass6_0`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+<>c__DisplayClass7_0`  

