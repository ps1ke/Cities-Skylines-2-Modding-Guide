# Colossal.IO.AssetDatabase.VirtualTexturing.UberZOrderer

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class UberZOrderer
{
    private Colossal.IO.AssetDatabase.VirtualTexturing.ZOrderer m_ZOrderer;
    private readonly System.Int32 m_MaxTextureSize;
    private readonly System.Int32 m_TotalNbBlocksPerReservation;
    private readonly System.Int32 m_MinTextureSize;
    private System.Int32[] m_SizePerLevel;
    private System.Int32[][] m_NbTextures;
    private System.Int32[][] m_CurrentTextureSizeInternalReservationIndex;
    private System.Int32[][] m_NbReservations;
    private System.Int32[][] m_LastTextureSizeInternalReservationIndex;
    private System.Int32[][][] m_NonSquareOffsetsPerEntry;
    private System.Int32[][][] m_NonSquareInternalOffsets;
    private System.Int32[] m_BaseIndices;
    private System.Int32 m_NbMidSizeMipLevelsForPacking;

    public System.Int32 TotalNbBlocks { get; }
    public System.Int32 NbReservedBlocks { get; }

    public UberZOrderer(System.Int32 minTextureSize, System.Int32 maxTextureSize, System.Int32 maxNbTextures, System.Int32 nbMidSizeMipLevelsForPacking);

    public System.Boolean CanReserveRect(System.Int32 textureWidth, System.Int32 textureHeight);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect GetAtlassedRect(System.Int32 index, System.Int32 textureWidth, System.Int32 textureHeight);
    public System.Int32 GetIndex(System.Int32 x, System.Int32 y);
    public UnityEngine.Rect GetRect(System.Int32 index, System.Int32 textureWidth, System.Int32 textureHeight, System.Single totalWidth, System.Single totalHeight);
    public System.Int32 ReserveRect(System.Int32 textureWidth, System.Int32 textureHeight);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.VirtualTexturing.ZOrderer m_ZOrderer`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.ZOrderer m_ZOrderer;
```

- `private readonly System.Int32 m_MaxTextureSize`  

```csharp
private readonly System.Int32 m_MaxTextureSize;
```

- `private readonly System.Int32 m_TotalNbBlocksPerReservation`  

```csharp
private readonly System.Int32 m_TotalNbBlocksPerReservation;
```

- `private readonly System.Int32 m_MinTextureSize`  

```csharp
private readonly System.Int32 m_MinTextureSize;
```

- `private System.Int32[] m_SizePerLevel`  

```csharp
private System.Int32[] m_SizePerLevel;
```

- `private System.Int32[][] m_NbTextures`  

```csharp
private System.Int32[][] m_NbTextures;
```

- `private System.Int32[][] m_CurrentTextureSizeInternalReservationIndex`  

```csharp
private System.Int32[][] m_CurrentTextureSizeInternalReservationIndex;
```

- `private System.Int32[][] m_NbReservations`  

```csharp
private System.Int32[][] m_NbReservations;
```

- `private System.Int32[][] m_LastTextureSizeInternalReservationIndex`  

```csharp
private System.Int32[][] m_LastTextureSizeInternalReservationIndex;
```

- `private System.Int32[][][] m_NonSquareOffsetsPerEntry`  

```csharp
private System.Int32[][][] m_NonSquareOffsetsPerEntry;
```

- `private System.Int32[][][] m_NonSquareInternalOffsets`  

```csharp
private System.Int32[][][] m_NonSquareInternalOffsets;
```

- `private System.Int32[] m_BaseIndices`  

```csharp
private System.Int32[] m_BaseIndices;
```

- `private System.Int32 m_NbMidSizeMipLevelsForPacking`  

```csharp
private System.Int32 m_NbMidSizeMipLevelsForPacking;
```


## Properties

- `public System.Int32 TotalNbBlocks { get }`  

```csharp
public System.Int32 TotalNbBlocks { get; }
```

- `public System.Int32 NbReservedBlocks { get }`  

```csharp
public System.Int32 NbReservedBlocks { get; }
```


## Constructors

- `public UberZOrderer(System.Int32 minTextureSize, System.Int32 maxTextureSize, System.Int32 maxNbTextures, System.Int32 nbMidSizeMipLevelsForPacking)`  

```csharp
public UberZOrderer(System.Int32 minTextureSize, System.Int32 maxTextureSize, System.Int32 maxNbTextures, System.Int32 nbMidSizeMipLevelsForPacking);
```


## Methods

- `public CanReserveRect(System.Int32 textureWidth, System.Int32 textureHeight) : System.Boolean`  

```csharp
public System.Boolean CanReserveRect(System.Int32 textureWidth, System.Int32 textureHeight);
```

- `public GetAtlassedRect(System.Int32 index, System.Int32 textureWidth, System.Int32 textureHeight) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect GetAtlassedRect(System.Int32 index, System.Int32 textureWidth, System.Int32 textureHeight);
```

- `public GetIndex(System.Int32 x, System.Int32 y) : System.Int32`  

```csharp
public System.Int32 GetIndex(System.Int32 x, System.Int32 y);
```

- `public GetRect(System.Int32 index, System.Int32 textureWidth, System.Int32 textureHeight, System.Single totalWidth, System.Single totalHeight) : UnityEngine.Rect`  

```csharp
public UnityEngine.Rect GetRect(System.Int32 index, System.Int32 textureWidth, System.Int32 textureHeight, System.Single totalWidth, System.Single totalHeight);
```

- `public ReserveRect(System.Int32 textureWidth, System.Int32 textureHeight) : System.Int32`  

```csharp
public System.Int32 ReserveRect(System.Int32 textureWidth, System.Int32 textureHeight);
```


