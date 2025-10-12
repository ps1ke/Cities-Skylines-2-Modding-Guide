# Colossal.AssetPipeline.PostProcessors.CharacterLODPostProcessor

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

- `public CharacterLODPostProcessor()`  

## Methods

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `public Execute(Colossal.AssetPipeline.Settings globalSettings, Colossal.AssetPipeline.PostProcessors.CharacterLODPostProcessor+PostProcessSettings settings, System.String assetRootPath, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.CharacterLODPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.CharacterLODPostProcessor+<>c__DisplayClass8_0`  

