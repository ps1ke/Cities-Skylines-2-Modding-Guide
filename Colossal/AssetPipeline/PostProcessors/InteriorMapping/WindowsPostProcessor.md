# Colossal.AssetPipeline.PostProcessors.InteriorMapping.WindowsPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.InteriorMapping`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IModelPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public class WindowsPostProcessor : Colossal.AssetPipeline.PostProcessors.IModelPostProcessor, Colossal.AssetPipeline.Importers.ISettingable
{
    private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute;

    public System.Int32 priority { get; }

    public WindowsPostProcessor();

    private static System.Void BakeInteriorWindows_Tangent(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
    private static System.Void BakeInteriorWindows_WindowSpace(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
    private static System.Void BakeInteriorWindows_WindowSpaceOverride(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
    private static System.Void BuildRooms(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> result, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Single MaxWindowDistance);
    private static System.Void BuildWindows(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island> islands, System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.Single floorHeight);
    public static System.Void BuildWindowsAndRooms(System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.ReadOnlySpan<System.Int32> indices, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& islands);
    private static System.Int32 Encode(System.Int32 Facing, System.Int32 roomId, System.Int32 Index);
    public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
    private System.Void Execute(Colossal.AssetPipeline.PostProcessors.InteriorMapping.WindowsPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
    private static System.Void ExtractFloors(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> outFloors, System.Single floorHeight);
    private static System.Void ExtractTriangles(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles, System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<System.Int32> indices);
    private static UnityEngine.Color32 FromInt(System.Int32 value);
    private static System.Void GenerateTrianglesAndIslands(System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<System.Int32> indices, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& islands);
    public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
    public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model);
    private static System.Void UpdateUVs(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 data, System.ReadOnlySpan<System.Int32> indices, Unity.Collections.NativeArray<UnityEngine.Color32> colors, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices, Unity.Collections.NativeArray<Unity.Mathematics.float2> uvs, Unity.Collections.NativeArray<Unity.Mathematics.float3> windowNormals, Unity.Collections.NativeArray<Unity.Mathematics.float4> windowTangents, Unity.Mathematics.float3 tangent, Unity.Mathematics.float3 up, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 center, System.Single width, System.Single height);
    private static System.Void UpdateUVs(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 data, System.ReadOnlySpan<System.Int32> indices, Unity.Collections.NativeArray<UnityEngine.Color32> colors, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices, Unity.Collections.NativeArray<Unity.Mathematics.float4> uvs, Unity.Collections.NativeArray<Unity.Mathematics.quaternion> windowRotation, Unity.Mathematics.float3 tangent, Unity.Mathematics.float3 up, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 center, System.Single width, System.Single height);
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

- `public WindowsPostProcessor()`  

```csharp
public WindowsPostProcessor();
```


## Methods

- `private static BakeInteriorWindows_Tangent(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors) : System.Void`  

```csharp
private static System.Void BakeInteriorWindows_Tangent(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
```

- `private static BakeInteriorWindows_WindowSpace(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors) : System.Void`  

```csharp
private static System.Void BakeInteriorWindows_WindowSpace(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
```

- `private static BakeInteriorWindows_WindowSpaceOverride(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors) : System.Void`  

```csharp
private static System.Void BakeInteriorWindows_WindowSpaceOverride(Colossal.AssetPipeline.Importers.ModelImporter+Model source, System.Int32 subMesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
```

- `private static BuildRooms(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> result, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Single MaxWindowDistance) : System.Void`  

```csharp
private static System.Void BuildRooms(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> result, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Single MaxWindowDistance);
```

- `private static BuildWindows(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island> islands, System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.Single floorHeight) : System.Void`  

```csharp
private static System.Void BuildWindows(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island> islands, System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.Single floorHeight);
```

- `public static BuildWindowsAndRooms(System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.ReadOnlySpan<System.Int32> indices, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& islands) : System.Void`  

```csharp
public static System.Void BuildWindowsAndRooms(System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.ReadOnlySpan<System.Int32> indices, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room> rooms, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& islands);
```

- `private static Encode(System.Int32 Facing, System.Int32 roomId, System.Int32 Index) : System.Int32`  

```csharp
private static System.Int32 Encode(System.Int32 Facing, System.Int32 roomId, System.Int32 Index);
```

- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  

```csharp
public System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```

- `private Execute(Colossal.AssetPipeline.PostProcessors.InteriorMapping.WindowsPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  

```csharp
private System.Void Execute(Colossal.AssetPipeline.PostProcessors.InteriorMapping.WindowsPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```

- `private static ExtractFloors(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> outFloors, System.Single floorHeight) : System.Void`  

```csharp
private static System.Void ExtractFloors(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> windows, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> outFloors, System.Single floorHeight);
```

- `private static ExtractTriangles(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles, System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<System.Int32> indices) : System.Void`  

```csharp
private static System.Void ExtractTriangles(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles, System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<System.Int32> indices);
```

- `private static FromInt(System.Int32 value) : UnityEngine.Color32`  

```csharp
private static UnityEngine.Color32 FromInt(System.Int32 value);
```

- `private static GenerateTrianglesAndIslands(System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<System.Int32> indices, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& islands) : System.Void`  

```csharp
private static System.Void GenerateTrianglesAndIslands(System.ReadOnlySpan<Unity.Mathematics.float3> vertices, System.ReadOnlySpan<System.Int32> indices, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& islands);
```

- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  

```csharp
public Colossal.AssetPipeline.Importers.ISettings GetDefaultSettings();
```

- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model) : System.Boolean`  

```csharp
public System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model);
```

- `private static UpdateUVs(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 data, System.ReadOnlySpan<System.Int32> indices, Unity.Collections.NativeArray<UnityEngine.Color32> colors, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices, Unity.Collections.NativeArray<Unity.Mathematics.float2> uvs, Unity.Collections.NativeArray<Unity.Mathematics.float3> windowNormals, Unity.Collections.NativeArray<Unity.Mathematics.float4> windowTangents, Unity.Mathematics.float3 tangent, Unity.Mathematics.float3 up, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 center, System.Single width, System.Single height) : System.Void`  

```csharp
private static System.Void UpdateUVs(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 data, System.ReadOnlySpan<System.Int32> indices, Unity.Collections.NativeArray<UnityEngine.Color32> colors, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices, Unity.Collections.NativeArray<Unity.Mathematics.float2> uvs, Unity.Collections.NativeArray<Unity.Mathematics.float3> windowNormals, Unity.Collections.NativeArray<Unity.Mathematics.float4> windowTangents, Unity.Mathematics.float3 tangent, Unity.Mathematics.float3 up, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 center, System.Single width, System.Single height);
```

- `private static UpdateUVs(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 data, System.ReadOnlySpan<System.Int32> indices, Unity.Collections.NativeArray<UnityEngine.Color32> colors, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices, Unity.Collections.NativeArray<Unity.Mathematics.float4> uvs, Unity.Collections.NativeArray<Unity.Mathematics.quaternion> windowRotation, Unity.Mathematics.float3 tangent, Unity.Mathematics.float3 up, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 center, System.Single width, System.Single height) : System.Void`  

```csharp
private static System.Void UpdateUVs(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 data, System.ReadOnlySpan<System.Int32> indices, Unity.Collections.NativeArray<UnityEngine.Color32> colors, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices, Unity.Collections.NativeArray<Unity.Mathematics.float4> uvs, Unity.Collections.NativeArray<Unity.Mathematics.quaternion> windowRotation, Unity.Mathematics.float3 tangent, Unity.Mathematics.float3 up, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 center, System.Single width, System.Single height);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.WindowsPostProcessor+DebugData`  
- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.WindowsPostProcessor+BakeMode`  
- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.WindowsPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.WindowsPostProcessor+<>c`  

