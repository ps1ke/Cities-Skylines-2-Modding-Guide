# Colossal.IO.AssetDatabase.VTSurfaceDataHandler

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class VTSurfaceDataHandler : System.IDisposable
{
    private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+Data m_Data;
    private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+FooterData m_FooterData;
    private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+LayerTempData[][] m_LayerTempDatas;
    private System.Boolean m_HasData;
    private static const System.UInt16 kFormatVersion;

    public Colossal.Hash128 MaterialAssetGuid { get; }
    public System.Boolean hasData { get; }

    public VTSurfaceDataHandler();

    public System.Void AddToSystem(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize textureSize, System.String filePath, System.Int64 fileOffset, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 nbPreProcessedMidMipLevels);
    public System.Void Dispose();
    public System.Void FillDebugMaterial(System.IO.BinaryReader perMaterialStreamReader, UnityEngine.Material material, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize GetTextureSize(System.Int32 stackConfigIndex);
    public System.Boolean HandledByVTSurfaceData(System.Int32 stackConfigIndex, System.Int32 layerIndex);
    public System.Void InitializeToUpdateMipBias(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textureMap, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, System.Int32 mipBias);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize[] InitializeToWrite(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textureMap, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesCount, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, System.Int32 mipBias);
    public System.Void ReadFooter(System.IO.BinaryReader sr);
    public System.Void ReadHeader(System.IO.BinaryReader sr);
    public System.Void WriteFile(System.IO.Stream stream);
    private System.Void WriteFooter(System.IO.BinaryWriter sw);
    private System.Void WriteHeader(System.IO.BinaryWriter sw);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+Data m_Data`  

```csharp
private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+Data m_Data;
```

- `private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+FooterData m_FooterData`  

```csharp
private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+FooterData m_FooterData;
```

- `private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+LayerTempData[][] m_LayerTempDatas`  

```csharp
private Colossal.IO.AssetDatabase.VTSurfaceDataHandler+LayerTempData[][] m_LayerTempDatas;
```

- `private System.Boolean m_HasData`  

```csharp
private System.Boolean m_HasData;
```

- `private static const System.UInt16 kFormatVersion`  

```csharp
private static const System.UInt16 kFormatVersion;
```


## Properties

- `public Colossal.Hash128 MaterialAssetGuid { get }`  

```csharp
public Colossal.Hash128 MaterialAssetGuid { get; }
```

- `public System.Boolean hasData { get }`  

```csharp
public System.Boolean hasData { get; }
```


## Constructors

- `public VTSurfaceDataHandler()`  

```csharp
public VTSurfaceDataHandler();
```


## Methods

- `public AddToSystem(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize textureSize, System.String filePath, System.Int64 fileOffset, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  

```csharp
public System.Void AddToSystem(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize textureSize, System.String filePath, System.Int64 fileOffset, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 nbPreProcessedMidMipLevels);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public FillDebugMaterial(System.IO.BinaryReader perMaterialStreamReader, UnityEngine.Material material, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData) : System.Void`  

```csharp
public System.Void FillDebugMaterial(System.IO.BinaryReader perMaterialStreamReader, UnityEngine.Material material, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData);
```

- `public GetTextureSize(System.Int32 stackConfigIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize GetTextureSize(System.Int32 stackConfigIndex);
```

- `public HandledByVTSurfaceData(System.Int32 stackConfigIndex, System.Int32 layerIndex) : System.Boolean`  

```csharp
public System.Boolean HandledByVTSurfaceData(System.Int32 stackConfigIndex, System.Int32 layerIndex);
```

- `public InitializeToUpdateMipBias(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textureMap, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, System.Int32 mipBias) : System.Void`  

```csharp
public System.Void InitializeToUpdateMipBias(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textureMap, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, System.Int32 mipBias);
```

- `public InitializeToWrite(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textureMap, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesCount, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, System.Int32 mipBias) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize[]`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize[] InitializeToWrite(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textureMap, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesCount, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, System.Int32 mipBias);
```

- `public ReadFooter(System.IO.BinaryReader sr) : System.Void`  

```csharp
public System.Void ReadFooter(System.IO.BinaryReader sr);
```

- `public ReadHeader(System.IO.BinaryReader sr) : System.Void`  

```csharp
public System.Void ReadHeader(System.IO.BinaryReader sr);
```

- `public WriteFile(System.IO.Stream stream) : System.Void`  

```csharp
public System.Void WriteFile(System.IO.Stream stream);
```

- `private WriteFooter(System.IO.BinaryWriter sw) : System.Void`  

```csharp
private System.Void WriteFooter(System.IO.BinaryWriter sw);
```

- `private WriteHeader(System.IO.BinaryWriter sw) : System.Void`  

```csharp
private System.Void WriteHeader(System.IO.BinaryWriter sw);
```


## Nested types

- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+StackData`  
- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+LayerTempData`  
- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+LayerData`  
- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+FooterData`  
- `Colossal.IO.AssetDatabase.VTSurfaceDataHandler+Data`  

