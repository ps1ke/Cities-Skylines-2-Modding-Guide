# Colossal.AssetPipeline.PostProcessors.SkinPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  

## Properties

- `public System.Int32 priority { get }`  

## Constructors

- `public SkinPostProcessor()`  

## Methods

- `private static CalculateDepth(Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] model, System.Int32 boneIndex) : System.Int32`  
- `private static CheckSkinning(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Void`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `private static GenerateGenericRig(Colossal.AssetPipeline.Importers.ModelImporter+Model model, System.Int32 rootBoneIndex) : System.Void`  
- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `private static MergeBoneInfos(System.Collections.Generic.List<Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]> bonesPerModel, System.Collections.Generic.List`1[[System.Collections.Generic.Dictionary`2[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& remappings) : Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]`  
- `private static PatchSkinning(Colossal.AssetPipeline.Geometry geometry, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Void`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.SkinPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.SkinPostProcessor+<>c`  
- `Colossal.AssetPipeline.PostProcessors.SkinPostProcessor+<>c__DisplayClass9_0`  
- `Colossal.AssetPipeline.PostProcessors.SkinPostProcessor+<>c__DisplayClass9_1`  

