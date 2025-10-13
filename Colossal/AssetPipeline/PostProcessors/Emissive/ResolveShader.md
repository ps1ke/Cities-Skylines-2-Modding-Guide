# Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.Emissive.TriangleRaster+IShader`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ResolveShader : Colossal.AssetPipeline.PostProcessors.Emissive.TriangleRaster+IShader
{
    public Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source;
    public Unity.Collections.NativeArray<System.UInt32> rasterTarget;
    public UnityEngine.Vector4 intensity;
    public UnityEngine.Color32 layerID;

    public System.Void Execute(System.Int32 x, System.Int32 y, System.Int32 lineIdx);
    public static System.Void ExecuteBurst(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
    public static System.Void ExecuteBurst$BurstManaged(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
}
```


## Fields

- `public Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source`  

```csharp
public Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source;
```

- `public Unity.Collections.NativeArray<System.UInt32> rasterTarget`  

```csharp
public Unity.Collections.NativeArray<System.UInt32> rasterTarget;
```

- `public UnityEngine.Vector4 intensity`  

```csharp
public UnityEngine.Vector4 intensity;
```

- `public UnityEngine.Color32 layerID`  

```csharp
public UnityEngine.Color32 layerID;
```


## Methods

- `public Execute(System.Int32 x, System.Int32 y, System.Int32 lineIdx) : System.Void`  

```csharp
public System.Void Execute(System.Int32 x, System.Int32 y, System.Int32 lineIdx);
```

- `public static ExecuteBurst(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2) : System.Void`  

```csharp
public static System.Void ExecuteBurst(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
```

- `public static ExecuteBurst$BurstManaged(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2) : System.Void`  

```csharp
public static System.Void ExecuteBurst$BurstManaged(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader+ExecuteBurst_000002F7$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader+ExecuteBurst_000002F7$BurstDirectCall`  

