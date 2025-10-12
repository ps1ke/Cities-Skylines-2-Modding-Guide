# Colossal.Rendering.VTTextureRequester

**Assembly:** `Game`  
**Namespace:** `Colossal.Rendering`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Unity.Collections.NativeList<System.Int32>[] m_TexturesIndices`  
- `private Unity.Collections.NativeList<System.Int32>[] m_StackGlobalIndices`  
- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>[] m_TextureBounds`  
- `private Unity.Collections.NativeList<System.Single>[] m_TexturesMaxPixels`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem`  
- `private System.Int32 m_RequestedThisFrame`  

## Properties

- `public System.Int32 stacksCount { get }`  
- `public System.Int32 registeredCount { get }`  
- `public System.Int32 requestCount { get }`  
- `public Unity.Collections.NativeList<System.Single>[] TexturesMaxPixels { get }`  

## Constructors

- `public VTTextureRequester(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem)`  

## Methods

- `public Clear() : System.Void`  
- `public Dispose() : System.Void`  
- `public GetTextureIndex(System.Int32 stackIndex, System.Int32 texturesIndex) : System.Int32`  
- `public RegisterTexture(System.Int32 stackConfigIndex, System.Int32 stackGlobalIndex, System.Int32 vtIndex, Colossal.Mathematics.Bounds2 bounds) : System.Int32`  
- `public UpdateMaxPixel(System.Int32 stackIndex, System.Int32 texturesIndex, System.Single maxPixel) : System.Void`  
- `public UpdateTexturesVTRequests() : System.Void`  

