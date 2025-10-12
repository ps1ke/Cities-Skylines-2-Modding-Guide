# Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper> m_AtlasMaterialsGroupers`  
- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper> m_RegisteredAtlasMaterialsGroupers`  
- `private System.Int32 m_AsyncTextureReadCount`  
- `private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo>[] m_RegisteredTextures`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry>> m_PreprocessedMidMipTilesInfo`  
- `private static readonly Colossal.Logging.ILog log`  

## Properties

- `public System.Boolean IsInitialized { get }`  
- `public System.Int32 midMipLevelsCount { get }`  
- `public System.Int32 asyncTextureReadCount { get }`  

## Constructors

- `public AtlasMaterialsDatabase(System.Int32 tileSize, System.Int32 midMipsCount, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.MidMipCacheAsset> midMipCacheAssets)`  

## Methods

- `public AddMidMipCache(System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.MidMipCacheAsset asset) : System.Void`  
- `private ClearRegisteredAtlasMaterialsGroupers() : System.Void`  
- `public static CountBits(System.Int32 n) : System.Int32`  
- `public FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  
- `private IsCacheAlreadyAdded(Colossal.IO.AssetDatabase.MidMipCacheAsset asset) : System.Boolean`  
- `public IsDuplicate(Colossal.Hash128 materialGuid) : System.Boolean`  
- `public IsHandlingMaterial(Colossal.Hash128 materialGuid) : System.Boolean`  
- `public PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem) : System.Void`  
- `public PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 nbMidMipLevels, System.Int32 baseMaxGroupSize, System.Int32 stackIndex, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory> categories, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo> registeredTextures, Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper grouper, System.Int32& tileIndex) : System.Void`  
- `public Reset() : System.Void`  
- `public SetPreReservedIndex(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset) : System.Boolean`  
- `public TryGetMidMipMask(System.Int32 stackGlobalIndex, System.Int32 universalTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry& objectEntry) : System.Boolean`  

## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsDatabase+<>c`  

