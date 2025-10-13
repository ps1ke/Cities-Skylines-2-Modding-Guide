# Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AtlasCategory
{
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup> m_AtlasMaskGroups;
    private readonly Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize m_Size;
    private Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] m_GroupedEntries;
    private System.Int32 m_EntriesCount;
    private System.Int32 m_TilesCount;
    private System.Int32 m_FirstTileIndex;
    private readonly System.Boolean m_PreProcessedMidMipDisabled;
    private readonly System.Int32 m_MipBiasOverride;
    private Unity.Collections.NativeArray<System.Byte>[] m_Tiles;

    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size { get; }
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] groupedEntries { get; }
    public System.Int32 entriesCount { get; }
    public System.Int32 tilesCount { get; set; }
    public System.Int32 firstTileIndex { get; set; }
    public System.Boolean preProcessedMidMipDisabled { get; }
    public System.Boolean hasMipBiasOverride { get; }
    public System.Int32 mipBiasOverride { get; }

    public AtlasCategory(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size, System.Int32 mipBiasOverride);
    public AtlasCategory(System.IO.BinaryReader br);

    public System.Void Add(System.Int32 multiStackLayersMask, System.Guid materialGuid);
    public System.Void Add(System.Int32 multiStackLayersMask, Colossal.Hash128 materialGuid, System.Int64 textureHash);
    private System.Void AddGroupData(System.Int32 nbSrcColumns, System.Int32 nbSrcRows, System.Int32 stackConfigIndex, System.Int32 nbMidMipLevels, Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] atlasEntries, System.Int32 startIndex, System.Int32 qty, System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> preProcessedTiles, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures);
    public System.Int32 CountGroups(System.Int32 maxGroupSize);
    public static System.Int32 GetTileIndex(System.Int32 entryIndex, System.Int32 srcColumn, System.Int32 srcRow, System.Int32 bigToSmallRatio, System.Int32 xStep, System.Int32 yStep);
    public System.Void GroupEntries(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize atlassedSize, System.Int32 stackConfigIndex, System.Int32 nbMidLevels, System.Int32 maxGroupSize, System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> preprocessedTiles, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures);
    public System.Boolean Match(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size);
    public System.Int32 ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures);
    public System.Void Write(System.IO.BinaryWriter bw);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup> m_AtlasMaskGroups`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup> m_AtlasMaskGroups;
```

- `private readonly Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize m_Size`  

```csharp
private readonly Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize m_Size;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] m_GroupedEntries`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] m_GroupedEntries;
```

- `private System.Int32 m_EntriesCount`  

```csharp
private System.Int32 m_EntriesCount;
```

- `private System.Int32 m_TilesCount`  

```csharp
private System.Int32 m_TilesCount;
```

- `private System.Int32 m_FirstTileIndex`  

```csharp
private System.Int32 m_FirstTileIndex;
```

- `private readonly System.Boolean m_PreProcessedMidMipDisabled`  

```csharp
private readonly System.Boolean m_PreProcessedMidMipDisabled;
```

- `private readonly System.Int32 m_MipBiasOverride`  

```csharp
private readonly System.Int32 m_MipBiasOverride;
```

- `private Unity.Collections.NativeArray<System.Byte>[] m_Tiles`  

```csharp
private Unity.Collections.NativeArray<System.Byte>[] m_Tiles;
```


## Properties

- `public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size { get }`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size { get; }
```

- `public Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] groupedEntries { get }`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] groupedEntries { get; }
```

- `public System.Int32 entriesCount { get }`  

```csharp
public System.Int32 entriesCount { get; }
```

- `public System.Int32 tilesCount { get; set }`  

```csharp
public System.Int32 tilesCount { get; set; }
```

- `public System.Int32 firstTileIndex { get; set }`  

```csharp
public System.Int32 firstTileIndex { get; set; }
```

- `public System.Boolean preProcessedMidMipDisabled { get }`  

```csharp
public System.Boolean preProcessedMidMipDisabled { get; }
```

- `public System.Boolean hasMipBiasOverride { get }`  

```csharp
public System.Boolean hasMipBiasOverride { get; }
```

- `public System.Int32 mipBiasOverride { get }`  

```csharp
public System.Int32 mipBiasOverride { get; }
```


## Constructors

- `public AtlasCategory(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size, System.Int32 mipBiasOverride = -1)`  

```csharp
public AtlasCategory(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size, System.Int32 mipBiasOverride);
```

- `public AtlasCategory(System.IO.BinaryReader br)`  

```csharp
public AtlasCategory(System.IO.BinaryReader br);
```


## Methods

- `public Add(System.Int32 multiStackLayersMask, System.Guid materialGuid) : System.Void`  

```csharp
public System.Void Add(System.Int32 multiStackLayersMask, System.Guid materialGuid);
```

- `public Add(System.Int32 multiStackLayersMask, Colossal.Hash128 materialGuid, System.Int64 textureHash) : System.Void`  

```csharp
public System.Void Add(System.Int32 multiStackLayersMask, Colossal.Hash128 materialGuid, System.Int64 textureHash);
```

- `private AddGroupData(System.Int32 nbSrcColumns, System.Int32 nbSrcRows, System.Int32 stackConfigIndex, System.Int32 nbMidMipLevels, Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] atlasEntries, System.Int32 startIndex, System.Int32 qty, System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> preProcessedTiles, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures) : System.Void`  

```csharp
private System.Void AddGroupData(System.Int32 nbSrcColumns, System.Int32 nbSrcRows, System.Int32 stackConfigIndex, System.Int32 nbMidMipLevels, Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry[] atlasEntries, System.Int32 startIndex, System.Int32 qty, System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> preProcessedTiles, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures);
```

- `public CountGroups(System.Int32 maxGroupSize) : System.Int32`  

```csharp
public System.Int32 CountGroups(System.Int32 maxGroupSize);
```

- `public static GetTileIndex(System.Int32 entryIndex, System.Int32 srcColumn, System.Int32 srcRow, System.Int32 bigToSmallRatio, System.Int32 xStep, System.Int32 yStep) : System.Int32`  

```csharp
public static System.Int32 GetTileIndex(System.Int32 entryIndex, System.Int32 srcColumn, System.Int32 srcRow, System.Int32 bigToSmallRatio, System.Int32 xStep, System.Int32 yStep);
```

- `public GroupEntries(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize atlassedSize, System.Int32 stackConfigIndex, System.Int32 nbMidLevels, System.Int32 maxGroupSize, System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> preprocessedTiles, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures) : System.Void`  

```csharp
public System.Void GroupEntries(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize atlassedSize, System.Int32 stackConfigIndex, System.Int32 nbMidLevels, System.Int32 maxGroupSize, System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> preprocessedTiles, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures);
```

- `public Match(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size) : System.Boolean`  

```csharp
public System.Boolean Match(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize size);
```

- `public ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures) : System.Int32`  

```csharp
public System.Int32 ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures);
```

- `public Write(System.IO.BinaryWriter bw) : System.Void`  

```csharp
public System.Void Write(System.IO.BinaryWriter bw);
```


