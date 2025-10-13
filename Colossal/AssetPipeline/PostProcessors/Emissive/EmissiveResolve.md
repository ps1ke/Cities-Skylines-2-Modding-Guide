# Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public static class EmissiveResolve
{
    private static readonly System.UInt32[] LinearToSRGBTable;
    private static readonly System.Single[] sRGBToLinear;

    public static System.Void BlitDilate(System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.UInt32> src, Unity.Collections.NativeArray<System.UInt32> dst, Unity.Collections.NativeArray<System.Byte> stencil);
    private static System.Void BlitDilateBurst(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.Byte* stencil);
    public static System.Void BlitDilateBurst$BurstManaged(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.Byte* stencil);
    public static System.Void BlitSmear(System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.UInt32> src, Unity.Collections.NativeArray<System.UInt32> dst);
    private static System.Void BlitSmearBurst(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst);
    public static System.Void BlitSmearBurst$BurstManaged(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst);
    private static System.Byte FloatToSRGB(System.Single val);
    private static System.UInt32 PackPixel(Unity.Mathematics.float4 c);
    private static Unity.Mathematics.float4 UnpackPixel(System.UInt32 pix);
}
```


## Fields

- `private static readonly System.UInt32[] LinearToSRGBTable`  

```csharp
private static readonly System.UInt32[] LinearToSRGBTable;
```

- `private static readonly System.Single[] sRGBToLinear`  

```csharp
private static readonly System.Single[] sRGBToLinear;
```


## Methods

- `public static BlitDilate(System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.UInt32> src, Unity.Collections.NativeArray<System.UInt32> dst, Unity.Collections.NativeArray<System.Byte> stencil) : System.Void`  

```csharp
public static System.Void BlitDilate(System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.UInt32> src, Unity.Collections.NativeArray<System.UInt32> dst, Unity.Collections.NativeArray<System.Byte> stencil);
```

- `private static BlitDilateBurst(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.Byte* stencil) : System.Void`  

```csharp
private static System.Void BlitDilateBurst(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.Byte* stencil);
```

- `public static BlitDilateBurst$BurstManaged(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.Byte* stencil) : System.Void`  

```csharp
public static System.Void BlitDilateBurst$BurstManaged(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.Byte* stencil);
```

- `public static BlitSmear(System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.UInt32> src, Unity.Collections.NativeArray<System.UInt32> dst) : System.Void`  

```csharp
public static System.Void BlitSmear(System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.UInt32> src, Unity.Collections.NativeArray<System.UInt32> dst);
```

- `private static BlitSmearBurst(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst) : System.Void`  

```csharp
private static System.Void BlitSmearBurst(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst);
```

- `public static BlitSmearBurst$BurstManaged(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst) : System.Void`  

```csharp
public static System.Void BlitSmearBurst$BurstManaged(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst);
```

- `private static FloatToSRGB(System.Single val) : System.Byte`  

```csharp
private static System.Byte FloatToSRGB(System.Single val);
```

- `private static PackPixel(Unity.Mathematics.float4 c) : System.UInt32`  

```csharp
private static System.UInt32 PackPixel(Unity.Mathematics.float4 c);
```

- `private static UnpackPixel(System.UInt32 pix) : Unity.Mathematics.float4`  

```csharp
private static Unity.Mathematics.float4 UnpackPixel(System.UInt32 pix);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitSmearBurst_000002F0$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitSmearBurst_000002F0$BurstDirectCall`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitDilateBurst_000002F2$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitDilateBurst_000002F2$BurstDirectCall`  

