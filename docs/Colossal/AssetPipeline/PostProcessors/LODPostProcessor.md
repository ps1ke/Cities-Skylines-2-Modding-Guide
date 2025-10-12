# Colossal.AssetPipeline.PostProcessors.LODPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODPrepare`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODRemesh`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODRemeshStep`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODOptimize`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfMeshOptSimplify`  

## Properties

- `public System.Int32 priority { get }`  

## Constructors

- `public LODPostProcessor()`  

## Methods

- `private ConvertMaterialsToInstaLOD(Colossal.AssetPipeline.Surface[] surfaces) : Colossal.InstaLOD.InstaLODMaterialData`  
- `private DoBake(Colossal.AssetPipeline.Settings globalSettings, System.String assetRootPath, Colossal.AssetPipeline.LOD baseLod, Colossal.AssetPipeline.Diagnostic.Report reportParent, Colossal.AssetPipeline.Diagnostic.Report+Asset reportAsset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs, System.String lodName, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.LODInputData> outInputData, System.Collections.Generic.List<Colossal.InstaLOD.Remeshing> outRemeshingOps, System.Collections.Generic.List<Colossal.AssetPipeline.Surface> outSurfaces) : System.Void`  
- `private DoBake(Colossal.AssetPipeline.Settings globalSettings, System.String assetRootPath, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.Diagnostic.Report reportParent, Colossal.AssetPipeline.Diagnostic.Report+Asset reportAsset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.InstaLOD.InstaLODMesh outputMesh, System.String lodName) : System.ValueTuple<Colossal.InstaLOD.Remeshing, Colossal.AssetPipeline.Surface>`  
- `private static DoSimplify(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs) : System.Single`  
- `private static DoSimplifyEdgeCollapse(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs) : System.Void`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `private Execute(Colossal.AssetPipeline.Settings globalSettings, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings settings, System.String assetRootPath, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `private static FindLodMethods(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings settings, System.Boolean& hasInstaLod, System.Boolean& hasMeshOpt) : System.Void`  
- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `private static IsGrassSurface(Colossal.AssetPipeline.Surface s) : System.Boolean`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets) : System.Boolean`  
- `private static ShouldSkipLevel(Colossal.AssetPipeline.Diagnostic.Report+Asset asset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, System.Int32 totalInputTris, System.Int32 level) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.LODPostProcessor+<>c`  

