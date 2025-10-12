# Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `BurstCompile`  

## Fields

- `private static readonly System.UInt32[] LinearToSRGBTable`  
- `private static readonly System.Single[] sRGBToLinear`  

## Methods

- `public static BlitDilate(System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.UInt32> src, Unity.Collections.NativeArray<System.UInt32> dst, Unity.Collections.NativeArray<System.Byte> stencil) : System.Void`  
- `private static BlitDilateBurst(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.Byte* stencil) : System.Void`  
- `public static BlitDilateBurst$BurstManaged(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst, System.Byte* stencil) : System.Void`  
- `public static BlitSmear(System.Int32 width, System.Int32 height, Unity.Collections.NativeArray<System.UInt32> src, Unity.Collections.NativeArray<System.UInt32> dst) : System.Void`  
- `private static BlitSmearBurst(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst) : System.Void`  
- `public static BlitSmearBurst$BurstManaged(System.Int32 width, System.Int32 height, System.UInt32* src, System.UInt32* dst) : System.Void`  
- `private static FloatToSRGB(System.Single val) : System.Byte`  
- `private static PackPixel(Unity.Mathematics.float4 c) : System.UInt32`  
- `private static UnpackPixel(System.UInt32 pix) : Unity.Mathematics.float4`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+ResolveShader`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+MarkStencilShader`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitSmearBurst_000002F0$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitSmearBurst_000002F0$BurstDirectCall`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitDilateBurst_000002F2$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveResolve+Colossal.AssetPipeline.PostProcessors.Emissive.BlitDilateBurst_000002F2$BurstDirectCall`  

