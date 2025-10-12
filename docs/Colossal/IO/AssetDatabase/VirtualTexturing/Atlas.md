# Colossal.IO.AssetDatabase.VirtualTexturing.Atlas

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Unity.Collections.NativeArray<System.Byte>>> m_HighMips`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.UberZOrderer m_ZOrderer`  
- `private readonly System.Int32 m_MaxTextureSize`  
- `private readonly System.Int32 m_PaddingSize`  
- `private System.Int32 m_HighestLevel`  
- `private readonly System.Int32 m_NbTexturesPerRow`  
- `private readonly System.Int32 m_NbRows`  
- `private readonly System.Int32 m_TotalSize`  
- `private readonly System.Int32 m_TileSize`  
- `private readonly System.Int32 m_NormalTileSizeInByte`  
- `private readonly System.Int32 m_TrilinearTileSizeInByte`  
- `private readonly Colossal.IO.AssetDatabase.VirtualTexturing.Atlas+AtlassedSizeCompact[] m_Sizes`  
- `private System.Int32 m_Width`  
- `private System.Int32 m_Height`  
- `private System.Int32 m_HighMipDataSize`  
- `private System.Int32[] m_NumberOfHighMipDataEntriesPerLayer`  
- `private System.Int32[] m_NumberOfHighMipDataEntriesPerLevel`  
- `private System.Int32[] m_NumberOfHighMipDataRequestsPerLevel`  
- `private System.Collections.Generic.List<System.Int32> m_ReservedTextureIndices`  

## Properties

- `public System.Int32 width { get }`  
- `public System.Int32 height { get }`  
- `public System.Int32 tileSize { get }`  
- `public System.Int32 normalTileSizeInByte { get }`  
- `public System.Int32 paddingSize { get }`  
- `public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Unity.Collections.NativeArray<System.Byte>>> highMips { get }`  
- `public System.Int32 TotalNbBlocks { get }`  
- `public System.Int32 NbReservedBlocks { get }`  
- `public System.Int32 HighMipDataSize { get }`  

## Constructors

- `public Atlas(System.Int32 width, System.Int32 height, System.Int32 maxTextureSize, System.Int32 tileSize, System.Int32 nbLayers, System.Int32 paddingSize, System.Int32 nbMidSizeMipLevelsForPacking)`  

## Methods

- `public AddTextureToCache(System.Int32 layerIndex, System.Int32 textureIndex, Unity.Collections.NativeArray<System.Byte> srcData, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 textureWidth, System.Int32 textureHeight, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  
- `public CanReserveTextureRect(System.Int32 width, System.Int32 height) : System.Boolean`  
- `public Destroy() : System.Void`  
- `public DuplicateTextureInCache(System.Int32 dstLayerIndex, System.Int32 dstTextureIndex, System.Int32 srcLayerIndex, System.Int32 srcTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.IO.AssetDatabase.VirtualTexturing.Atlas srcAtlas, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  
- `public FillFromCache(System.Int32 layerIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req) : System.Boolean`  
- `public FindRectIndex(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Int32`  
- `public GetAtlassedRect(System.Int32 index) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect`  
- `public GetHighMipData(System.Int32 layerIndex, System.Int32 column, System.Int32 row, System.Int32 level, System.Boolean asSource) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetRect(System.Int32 index) : UnityEngine.Rect`  
- `public GetTextureSize(System.Int32 index) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  
- `public ReserveMultipleTextureRect(System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment) : System.Collections.Generic.List<System.Int32>`  
- `public ReserveTextureRect(System.Int32 width, System.Int32 height) : System.Int32`  

## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.Atlas+AtlassedSizeCompact`  

