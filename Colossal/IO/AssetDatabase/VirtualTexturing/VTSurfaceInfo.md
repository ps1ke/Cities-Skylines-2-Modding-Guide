# Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class VTSurfaceInfo
{
    public readonly System.String path;
    public readonly System.Int64 tilesDataOffset;
    public readonly System.Int32[] dataOffsets;
    public readonly System.Int32[] dataSizes;
    public readonly System.Int32 tileCount;
    public readonly System.Collections.Generic.List<System.Int32> compressedTileOffsets;
    public System.Int32 actualWidth;
    public System.Int32 actualHeight;

    public VTSurfaceInfo(System.String path, System.Int64 tilesDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 tileCount, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height);

    public System.Void GetCompressedTileOffsetAndSize(System.Int32 tileIndex, System.Int64& offset, System.Int32& size);
    public System.Boolean HandledPerSurface(System.Int32 layerIndex);
}
```


## Fields

- `public readonly System.String path`  

```csharp
public readonly System.String path;
```

- `public readonly System.Int64 tilesDataOffset`  

```csharp
public readonly System.Int64 tilesDataOffset;
```

- `public readonly System.Int32[] dataOffsets`  

```csharp
public readonly System.Int32[] dataOffsets;
```

- `public readonly System.Int32[] dataSizes`  

```csharp
public readonly System.Int32[] dataSizes;
```

- `public readonly System.Int32 tileCount`  

```csharp
public readonly System.Int32 tileCount;
```

- `public readonly System.Collections.Generic.List<System.Int32> compressedTileOffsets`  

```csharp
public readonly System.Collections.Generic.List<System.Int32> compressedTileOffsets;
```

- `public System.Int32 actualWidth`  

```csharp
public System.Int32 actualWidth;
```

- `public System.Int32 actualHeight`  

```csharp
public System.Int32 actualHeight;
```


## Constructors

- `public VTSurfaceInfo(System.String path, System.Int64 tilesDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 tileCount, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height)`  

```csharp
public VTSurfaceInfo(System.String path, System.Int64 tilesDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 tileCount, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height);
```


## Methods

- `public GetCompressedTileOffsetAndSize(System.Int32 tileIndex, System.Int64& offset, System.Int32& size) : System.Void`  

```csharp
public System.Void GetCompressedTileOffsetAndSize(System.Int32 tileIndex, System.Int64& offset, System.Int32& size);
```

- `public HandledPerSurface(System.Int32 layerIndex) : System.Boolean`  

```csharp
public System.Boolean HandledPerSurface(System.Int32 layerIndex);
```


