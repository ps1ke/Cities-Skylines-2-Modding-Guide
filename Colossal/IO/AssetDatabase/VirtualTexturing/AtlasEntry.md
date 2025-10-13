# Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct AtlasEntry
{
    internal System.Int32 m_Mask;
    internal Colossal.Hash128 m_MaterialGuid;
    internal System.Int16 m_IndexInGroup;
    internal System.Int32[] m_FirstTileIndices;
    internal System.Int32[] m_GroupedMasks;
    internal Colossal.Hash128[] m_DuplicateMaterials;

    public AtlasEntry(System.Int32 mask, Colossal.Hash128 materialGuid, System.Int16 indexInGroup, System.Int32 nbMidMipLevels);
    public AtlasEntry(System.Int32 mask, Colossal.Hash128 materialGuid, System.Int16 indexInGroup, System.Int32 nbMidMipLevels, Colossal.Hash128[] duplicates);

}
```


## Fields

- `internal System.Int32 m_Mask`  

```csharp
internal System.Int32 m_Mask;
```

- `internal Colossal.Hash128 m_MaterialGuid`  

```csharp
internal Colossal.Hash128 m_MaterialGuid;
```

- `internal System.Int16 m_IndexInGroup`  

```csharp
internal System.Int16 m_IndexInGroup;
```

- `internal System.Int32[] m_FirstTileIndices`  

```csharp
internal System.Int32[] m_FirstTileIndices;
```

- `internal System.Int32[] m_GroupedMasks`  

```csharp
internal System.Int32[] m_GroupedMasks;
```

- `internal Colossal.Hash128[] m_DuplicateMaterials`  

```csharp
internal Colossal.Hash128[] m_DuplicateMaterials;
```


## Constructors

- `public AtlasEntry(System.Int32 mask, Colossal.Hash128 materialGuid, System.Int16 indexInGroup, System.Int32 nbMidMipLevels)`  

```csharp
public AtlasEntry(System.Int32 mask, Colossal.Hash128 materialGuid, System.Int16 indexInGroup, System.Int32 nbMidMipLevels);
```

- `public AtlasEntry(System.Int32 mask, Colossal.Hash128 materialGuid, System.Int16 indexInGroup, System.Int32 nbMidMipLevels, Colossal.Hash128[] duplicates)`  

```csharp
public AtlasEntry(System.Int32 mask, Colossal.Hash128 materialGuid, System.Int16 indexInGroup, System.Int32 nbMidMipLevels, Colossal.Hash128[] duplicates);
```


