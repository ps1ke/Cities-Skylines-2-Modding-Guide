# Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AtlasMaterialsDatabase
{
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper> m_AtlasMaterialsGroupers;
    private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper> m_RegisteredAtlasMaterialsGroupers;
    private System.Int32 m_AsyncTextureReadCount;
    private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo>[] m_RegisteredTextures;
    private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry>> m_PreprocessedMidMipTilesInfo;
    private static readonly Colossal.Logging.ILog log;

    public System.Boolean IsInitialized { get; }
    public System.Int32 midMipLevelsCount { get; }
    public System.Int32 asyncTextureReadCount { get; }

    public AtlasMaterialsDatabase(System.Int32 tileSize, System.Int32 midMipsCount, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.MidMipCacheAsset> midMipCacheAssets);

    public System.Void AddMidMipCache(System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.MidMipCacheAsset asset);
    private System.Void ClearRegisteredAtlasMaterialsGroupers();
    public static System.Int32 CountBits(System.Int32 n);
    public System.Void FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
    private System.Boolean IsCacheAlreadyAdded(Colossal.IO.AssetDatabase.MidMipCacheAsset asset);
    public System.Boolean IsDuplicate(Colossal.Hash128 materialGuid);
    public System.Boolean IsHandlingMaterial(Colossal.Hash128 materialGuid);
    public System.Void PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem);
    public System.Void PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 nbMidMipLevels, System.Int32 baseMaxGroupSize, System.Int32 stackIndex, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory> categories, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo> registeredTextures, Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper grouper, System.Int32& tileIndex);
    public System.Void Reset();
    public System.Boolean SetPreReservedIndex(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset);
    public System.Boolean TryGetMidMipMask(System.Int32 stackGlobalIndex, System.Int32 universalTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry& objectEntry);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper> m_AtlasMaterialsGroupers`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper> m_AtlasMaterialsGroupers;
```

- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper> m_RegisteredAtlasMaterialsGroupers`  

```csharp
private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper> m_RegisteredAtlasMaterialsGroupers;
```

- `private System.Int32 m_AsyncTextureReadCount`  

```csharp
private System.Int32 m_AsyncTextureReadCount;
```

- `private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo>[] m_RegisteredTextures`  

```csharp
private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo>[] m_RegisteredTextures;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry>> m_PreprocessedMidMipTilesInfo`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry>> m_PreprocessedMidMipTilesInfo;
```

- `private static readonly Colossal.Logging.ILog log`  

```csharp
private static readonly Colossal.Logging.ILog log;
```


## Properties

- `public System.Boolean IsInitialized { get }`  

```csharp
public System.Boolean IsInitialized { get; }
```

- `public System.Int32 midMipLevelsCount { get }`  

```csharp
public System.Int32 midMipLevelsCount { get; }
```

- `public System.Int32 asyncTextureReadCount { get }`  

```csharp
public System.Int32 asyncTextureReadCount { get; }
```


## Constructors

- `public AtlasMaterialsDatabase(System.Int32 tileSize, System.Int32 midMipsCount, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.MidMipCacheAsset> midMipCacheAssets)`  

```csharp
public AtlasMaterialsDatabase(System.Int32 tileSize, System.Int32 midMipsCount, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.MidMipCacheAsset> midMipCacheAssets);
```


## Methods

- `public AddMidMipCache(System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.MidMipCacheAsset asset) : System.Void`  

```csharp
public System.Void AddMidMipCache(System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.MidMipCacheAsset asset);
```

- `private ClearRegisteredAtlasMaterialsGroupers() : System.Void`  

```csharp
private System.Void ClearRegisteredAtlasMaterialsGroupers();
```

- `public static CountBits(System.Int32 n) : System.Int32`  

```csharp
public static System.Int32 CountBits(System.Int32 n);
```

- `public FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  

```csharp
public System.Void FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
```

- `private IsCacheAlreadyAdded(Colossal.IO.AssetDatabase.MidMipCacheAsset asset) : System.Boolean`  

```csharp
private System.Boolean IsCacheAlreadyAdded(Colossal.IO.AssetDatabase.MidMipCacheAsset asset);
```

- `public IsDuplicate(Colossal.Hash128 materialGuid) : System.Boolean`  

```csharp
public System.Boolean IsDuplicate(Colossal.Hash128 materialGuid);
```

- `public IsHandlingMaterial(Colossal.Hash128 materialGuid) : System.Boolean`  

```csharp
public System.Boolean IsHandlingMaterial(Colossal.Hash128 materialGuid);
```

- `public PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem) : System.Void`  

```csharp
public System.Void PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem);
```

- `public PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 nbMidMipLevels, System.Int32 baseMaxGroupSize, System.Int32 stackIndex, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory> categories, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo> registeredTextures, Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper grouper, System.Int32& tileIndex) : System.Void`  

```csharp
public System.Void PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 nbMidMipLevels, System.Int32 baseMaxGroupSize, System.Int32 stackIndex, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory> categories, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo> registeredTextures, Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper grouper, System.Int32& tileIndex);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public SetPreReservedIndex(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset) : System.Boolean`  

```csharp
public System.Boolean SetPreReservedIndex(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset);
```

- `public TryGetMidMipMask(System.Int32 stackGlobalIndex, System.Int32 universalTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry& objectEntry) : System.Boolean`  

```csharp
public System.Boolean TryGetMidMipMask(System.Int32 stackGlobalIndex, System.Int32 universalTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry& objectEntry);
```


## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsDatabase+<>c`  

