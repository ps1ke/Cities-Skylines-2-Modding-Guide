# Colossal.AssetPipeline.PostProcessors.LODPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public class LODPostProcessor : Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODPrepare;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODRemesh;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODRemeshStep;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODOptimize;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfMeshOptSimplify;

    public System.Int32 priority { get; }

    public LODPostProcessor();

    private Colossal.InstaLOD.InstaLODMaterialData ConvertMaterialsToInstaLOD(Colossal.AssetPipeline.Surface[] surfaces);
    private System.Void DoBake(Colossal.AssetPipeline.Settings globalSettings, System.String assetRootPath, Colossal.AssetPipeline.LOD baseLod, Colossal.AssetPipeline.Diagnostic.Report reportParent, Colossal.AssetPipeline.Diagnostic.Report+Asset reportAsset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs, System.String lodName, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.LODInputData> outInputData, System.Collections.Generic.List<Colossal.InstaLOD.Remeshing> outRemeshingOps, System.Collections.Generic.List<Colossal.AssetPipeline.Surface> outSurfaces);
    private System.ValueTuple<Colossal.InstaLOD.Remeshing, Colossal.AssetPipeline.Surface> DoBake(Colossal.AssetPipeline.Settings globalSettings, System.String assetRootPath, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.Diagnostic.Report reportParent, Colossal.AssetPipeline.Diagnostic.Report+Asset reportAsset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.InstaLOD.InstaLODMesh outputMesh, System.String lodName);
    private static System.Single DoSimplify(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs);
    private static System.Void DoSimplifyEdgeCollapse(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
    private System.Void Execute(Colossal.AssetPipeline.Settings globalSettings, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings settings, System.String assetRootPath, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
    private static System.Void FindLodMethods(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings settings, System.Boolean& hasInstaLod, System.Boolean& hasMeshOpt);
    public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    private static System.Boolean IsGrassSurface(Colossal.AssetPipeline.Surface s);
    public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets);
    private static System.Boolean ShouldSkipLevel(Colossal.AssetPipeline.Diagnostic.Report+Asset asset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, System.Int32 totalInputTris, System.Int32 level);
}
```


## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODPrepare`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODPrepare;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODRemesh`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODRemesh;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODRemeshStep`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODRemeshStep;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODOptimize`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfInstaLODOptimize;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfMeshOptSimplify`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfMeshOptSimplify;
```


## Properties

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```


## Constructors

- `public LODPostProcessor()`  

```csharp
public LODPostProcessor();
```


## Methods

- `private ConvertMaterialsToInstaLOD(Colossal.AssetPipeline.Surface[] surfaces) : Colossal.InstaLOD.InstaLODMaterialData`  

```csharp
private Colossal.InstaLOD.InstaLODMaterialData ConvertMaterialsToInstaLOD(Colossal.AssetPipeline.Surface[] surfaces);
```

- `private DoBake(Colossal.AssetPipeline.Settings globalSettings, System.String assetRootPath, Colossal.AssetPipeline.LOD baseLod, Colossal.AssetPipeline.Diagnostic.Report reportParent, Colossal.AssetPipeline.Diagnostic.Report+Asset reportAsset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs, System.String lodName, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.LODInputData> outInputData, System.Collections.Generic.List<Colossal.InstaLOD.Remeshing> outRemeshingOps, System.Collections.Generic.List<Colossal.AssetPipeline.Surface> outSurfaces) : System.Void`  

```csharp
private System.Void DoBake(Colossal.AssetPipeline.Settings globalSettings, System.String assetRootPath, Colossal.AssetPipeline.LOD baseLod, Colossal.AssetPipeline.Diagnostic.Report reportParent, Colossal.AssetPipeline.Diagnostic.Report+Asset reportAsset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs, System.String lodName, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.LODInputData> outInputData, System.Collections.Generic.List<Colossal.InstaLOD.Remeshing> outRemeshingOps, System.Collections.Generic.List<Colossal.AssetPipeline.Surface> outSurfaces);
```

- `private DoBake(Colossal.AssetPipeline.Settings globalSettings, System.String assetRootPath, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.Diagnostic.Report reportParent, Colossal.AssetPipeline.Diagnostic.Report+Asset reportAsset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.InstaLOD.InstaLODMesh outputMesh, System.String lodName) : System.ValueTuple<Colossal.InstaLOD.Remeshing, Colossal.AssetPipeline.Surface>`  

```csharp
private System.ValueTuple<Colossal.InstaLOD.Remeshing, Colossal.AssetPipeline.Surface> DoBake(Colossal.AssetPipeline.Settings globalSettings, System.String assetRootPath, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.Diagnostic.Report reportParent, Colossal.AssetPipeline.Diagnostic.Report+Asset reportAsset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.InstaLOD.InstaLODMesh outputMesh, System.String lodName);
```

- `private static DoSimplify(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs) : System.Single`  

```csharp
private static System.Single DoSimplify(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs);
```

- `private static DoSimplifyEdgeCollapse(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs) : System.Void`  

```csharp
private static System.Void DoSimplifyEdgeCollapse(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, Colossal.AssetPipeline.PostProcessors.LODInputData inputs, Colossal.AssetPipeline.PostProcessors.LODOutputData outputs);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
```

- `private Execute(Colossal.AssetPipeline.Settings globalSettings, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings settings, System.String assetRootPath, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  

```csharp
private System.Void Execute(Colossal.AssetPipeline.Settings globalSettings, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings settings, System.String assetRootPath, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
```

- `private static FindLodMethods(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings settings, System.Boolean& hasInstaLod, System.Boolean& hasMeshOpt) : System.Void`  

```csharp
private static System.Void FindLodMethods(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings settings, System.Boolean& hasInstaLod, System.Boolean& hasMeshOpt);
```

- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `private static IsGrassSurface(Colossal.AssetPipeline.Surface s) : System.Boolean`  

```csharp
private static System.Boolean IsGrassSurface(Colossal.AssetPipeline.Surface s);
```

- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets) : System.Boolean`  

```csharp
public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets);
```

- `private static ShouldSkipLevel(Colossal.AssetPipeline.Diagnostic.Report+Asset asset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, System.Int32 totalInputTris, System.Int32 level) : System.Boolean`  

```csharp
private static System.Boolean ShouldSkipLevel(Colossal.AssetPipeline.Diagnostic.Report+Asset asset, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings levelDesc, System.Int32 totalInputTris, System.Int32 level);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.LODPostProcessor+<>c`  

