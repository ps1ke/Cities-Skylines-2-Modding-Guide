# Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Wind`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public class WindBakingPostProcessor : Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;

    public System.Int32 priority { get; }

    public WindBakingPostProcessor();

    private System.Void BakeGeometry(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] report);
    private System.Void BakeHierarchyDecompose(Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Importers.ModelImporter+Model[]& models, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+WindPivotHelper dstPivots, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] surfaceReport);
    private System.Void BakeSingleDecompose(Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Importers.ModelImporter+Model[]& models, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+WindPivotHelper dstPivots, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] report);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
    public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    private static UnityEngine.Vector3 PackHierarchyPivotData(System.Boolean enable0, UnityEngine.Vector3 pos0, UnityEngine.Vector3 fwd0, System.Boolean enable1, UnityEngine.Vector3 pos1, UnityEngine.Vector3 fwd1);
    private static System.UInt32 PackSFloatToFixed(System.Single val, System.Single range, System.Int32 bits);
    private static System.UInt32 PackUFloatToFixed(System.Single val, System.Single range, System.Int32 bits);
    private static System.Void SetDefaultProperties(Colossal.AssetPipeline.Surface surface, System.Single height);
    public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets);
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

- `public WindBakingPostProcessor()`  

```csharp
public WindBakingPostProcessor();
```


## Methods

- `private BakeGeometry(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] report) : System.Void`  

```csharp
private System.Void BakeGeometry(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] report);
```

- `private BakeHierarchyDecompose(Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Importers.ModelImporter+Model[]& models, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+WindPivotHelper dstPivots, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] surfaceReport) : System.Void`  

```csharp
private System.Void BakeHierarchyDecompose(Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Importers.ModelImporter+Model[]& models, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+WindPivotHelper dstPivots, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] surfaceReport);
```

- `private BakeSingleDecompose(Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Importers.ModelImporter+Model[]& models, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+WindPivotHelper dstPivots, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] report) : System.Void`  

```csharp
private System.Void BakeSingleDecompose(Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Importers.ModelImporter+Model[]& models, Colossal.AssetPipeline.Surface[] surfaces, Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+WindPivotHelper dstPivots, Colossal.AssetPipeline.Diagnostic.Report+AssetData[] report);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
```

- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `private static PackHierarchyPivotData(System.Boolean enable0, UnityEngine.Vector3 pos0, UnityEngine.Vector3 fwd0, System.Boolean enable1, UnityEngine.Vector3 pos1, UnityEngine.Vector3 fwd1) : UnityEngine.Vector3`  

```csharp
private static UnityEngine.Vector3 PackHierarchyPivotData(System.Boolean enable0, UnityEngine.Vector3 pos0, UnityEngine.Vector3 fwd0, System.Boolean enable1, UnityEngine.Vector3 pos1, UnityEngine.Vector3 fwd1);
```

- `private static PackSFloatToFixed(System.Single val, System.Single range, System.Int32 bits) : System.UInt32`  

```csharp
private static System.UInt32 PackSFloatToFixed(System.Single val, System.Single range, System.Int32 bits);
```

- `private static PackUFloatToFixed(System.Single val, System.Single range, System.Int32 bits) : System.UInt32`  

```csharp
private static System.UInt32 PackUFloatToFixed(System.Single val, System.Single range, System.Int32 bits);
```

- `private static SetDefaultProperties(Colossal.AssetPipeline.Surface surface, System.Single height) : System.Void`  

```csharp
private static System.Void SetDefaultProperties(Colossal.AssetPipeline.Surface surface, System.Single height);
```

- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets) : System.Boolean`  

```csharp
public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+PivotBakeMode`  
- `Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+HierarchyPackedData`  
- `Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+WindPivotHelper`  
- `Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+<>c`  
- `Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+<>c__DisplayClass10_0`  
- `Colossal.AssetPipeline.PostProcessors.Wind.WindBakingPostProcessor+<>c__DisplayClass8_0`  

