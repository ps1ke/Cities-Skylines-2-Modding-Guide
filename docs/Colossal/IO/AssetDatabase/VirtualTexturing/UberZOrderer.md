# Colossal.IO.AssetDatabase.VirtualTexturing.UberZOrderer

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.IO.AssetDatabase.VirtualTexturing.ZOrderer m_ZOrderer`  
- `private readonly System.Int32 m_MaxTextureSize`  
- `private readonly System.Int32 m_TotalNbBlocksPerReservation`  
- `private readonly System.Int32 m_MinTextureSize`  
- `private System.Int32[] m_SizePerLevel`  
- `private System.Int32[][] m_NbTextures`  
- `private System.Int32[][] m_CurrentTextureSizeInternalReservationIndex`  
- `private System.Int32[][] m_NbReservations`  
- `private System.Int32[][] m_LastTextureSizeInternalReservationIndex`  
- `private System.Int32[][][] m_NonSquareOffsetsPerEntry`  
- `private System.Int32[][][] m_NonSquareInternalOffsets`  
- `private System.Int32[] m_BaseIndices`  
- `private System.Int32 m_NbMidSizeMipLevelsForPacking`  

## Properties

- `public System.Int32 TotalNbBlocks { get }`  
- `public System.Int32 NbReservedBlocks { get }`  

## Constructors

- `public UberZOrderer(System.Int32 minTextureSize, System.Int32 maxTextureSize, System.Int32 maxNbTextures, System.Int32 nbMidSizeMipLevelsForPacking)`  

## Methods

- `public CanReserveRect(System.Int32 textureWidth, System.Int32 textureHeight) : System.Boolean`  
- `public GetAtlassedRect(System.Int32 index, System.Int32 textureWidth, System.Int32 textureHeight) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect`  
- `public GetIndex(System.Int32 x, System.Int32 y) : System.Int32`  
- `public GetRect(System.Int32 index, System.Int32 textureWidth, System.Int32 textureHeight, System.Single totalWidth, System.Single totalHeight) : UnityEngine.Rect`  
- `public ReserveRect(System.Int32 textureWidth, System.Int32 textureHeight) : System.Int32`  

