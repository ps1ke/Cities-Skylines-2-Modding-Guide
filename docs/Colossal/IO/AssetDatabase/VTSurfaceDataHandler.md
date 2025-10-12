# Colossal.IO.AssetDatabase.VTSurfaceDataHandler

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+Data m_Data`  
- `private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+FooterData m_FooterData`  
- `private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+LayerTempData[][] m_LayerTempDatas`  
- `private System.Boolean m_HasData`  
- `private static const System.UInt16 kFormatVersion`  

## Properties

- `public Colossal.Hash128 MaterialAssetGuid { get }`  
- `public System.Boolean hasData { get }`  

## Constructors

- `public VTSurfaceDataHandler()`  

## Methods

- `public AddToSystem(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize textureSize, System.String filePath, System.Int64 fileOffset, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  
- `public Dispose() : System.Void`  
- `public FillDebugMaterial(System.IO.BinaryReader perMaterialStreamReader, UnityEngine.Material material, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData) : System.Void`  
- `public GetTextureSize(System.Int32 stackConfigIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  
- `public HandledByVTSurfaceData(System.Int32 stackConfigIndex, System.Int32 layerIndex) : System.Boolean`  
- `public InitializeToUpdateMipBias(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textureMap, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, System.Int32 mipBias) : System.Void`  
- `public InitializeToWrite(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textureMap, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesCount, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, System.Int32 mipBias) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize[]`  
- `public ReadFooter(System.IO.BinaryReader sr) : System.Void`  
- `public ReadHeader(System.IO.BinaryReader sr) : System.Void`  
- `public WriteFile(System.IO.Stream stream) : System.Void`  
- `private WriteFooter(System.IO.BinaryWriter sw) : System.Void`  
- `private WriteHeader(System.IO.BinaryWriter sw) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+StackData`  
- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+LayerTempData`  
- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+LayerData`  
- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+FooterData`  
- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+Data`  

