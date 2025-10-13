# Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.Emissive.TriangleRaster+IShader`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct MarkStencilShader : Colossal.AssetPipeline.PostProcessors.Emissive.TriangleRaster+IShader
{
    public Unity.Collections.NativeArray<System.Byte> stencilTarget;

    public System.Void Execute(System.Int32 x, System.Int32 y, System.Int32 lineIdx);
    public static System.Void ExecuteBurst(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
    public static System.Void ExecuteBurst$BurstManaged(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
}
```


## Fields

- `public Unity.Collections.NativeArray<System.Byte> stencilTarget`  

```csharp
public Unity.Collections.NativeArray<System.Byte> stencilTarget;
```


## Methods

- `public Execute(System.Int32 x, System.Int32 y, System.Int32 lineIdx) : System.Void`  

```csharp
public System.Void Execute(System.Int32 x, System.Int32 y, System.Int32 lineIdx);
```

- `public static ExecuteBurst(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2) : System.Void`  

```csharp
public static System.Void ExecuteBurst(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
```

- `public static ExecuteBurst$BurstManaged(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2) : System.Void`  

```csharp
public static System.Void ExecuteBurst$BurstManaged(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader& shader, System.Int32 width, System.Int32 height, Unity.Mathematics.float2& pt0, Unity.Mathematics.float2& pt1, Unity.Mathematics.float2& pt2);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader+ExecuteBurst_000002F9$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader+ExecuteBurst_000002F9$BurstDirectCall`  

