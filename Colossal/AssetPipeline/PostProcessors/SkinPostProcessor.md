# Colossal.AssetPipeline.PostProcessors.SkinPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public class SkinPostProcessor : Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;

    public System.Int32 priority { get; }

    public SkinPostProcessor();

    private static System.Int32 CalculateDepth(Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] model, System.Int32 boneIndex);
    private static System.Void CheckSkinning(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
    private static System.Void GenerateGenericRig(Colossal.AssetPipeline.Importers.ModelImporter+Model model, System.Int32 rootBoneIndex);
    public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    private static Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] MergeBoneInfos(System.Collections.Generic.List<Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]> bonesPerModel, System.Collections.Generic.List`1[[System.Collections.Generic.Dictionary`2[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& remappings);
    private static System.Void PatchSkinning(Colossal.AssetPipeline.Geometry geometry, Colossal.AssetPipeline.Diagnostic.ReportBase report);
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

- `public SkinPostProcessor()`  

```csharp
public SkinPostProcessor();
```


## Methods

- `private static CalculateDepth(Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] model, System.Int32 boneIndex) : System.Int32`  

```csharp
private static System.Int32 CalculateDepth(Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] model, System.Int32 boneIndex);
```

- `private static CheckSkinning(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Void`  

```csharp
private static System.Void CheckSkinning(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
```

- `private static GenerateGenericRig(Colossal.AssetPipeline.Importers.ModelImporter+Model model, System.Int32 rootBoneIndex) : System.Void`  

```csharp
private static System.Void GenerateGenericRig(Colossal.AssetPipeline.Importers.ModelImporter+Model model, System.Int32 rootBoneIndex);
```

- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `private static MergeBoneInfos(System.Collections.Generic.List<Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]> bonesPerModel, System.Collections.Generic.List`1[[System.Collections.Generic.Dictionary`2[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& remappings) : Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]`  

```csharp
private static Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] MergeBoneInfos(System.Collections.Generic.List<Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]> bonesPerModel, System.Collections.Generic.List`1[[System.Collections.Generic.Dictionary`2[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& remappings);
```

- `private static PatchSkinning(Colossal.AssetPipeline.Geometry geometry, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Void`  

```csharp
private static System.Void PatchSkinning(Colossal.AssetPipeline.Geometry geometry, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets) : System.Boolean`  

```csharp
public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.SkinPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.SkinPostProcessor+<>c`  
- `Colossal.AssetPipeline.PostProcessors.SkinPostProcessor+<>c__DisplayClass9_0`  
- `Colossal.AssetPipeline.PostProcessors.SkinPostProcessor+<>c__DisplayClass9_1`  

