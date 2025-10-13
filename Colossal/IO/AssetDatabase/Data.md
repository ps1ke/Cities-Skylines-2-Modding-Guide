# Colossal.IO.AssetDatabase.GeometryAsset+Data

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct Data : System.IDisposable
{
    public System.Int32 meshCount;
    public System.UInt32 fileFlags;
    public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader> meshInfos;
    public System.Int32 shapeCount;
    public System.Int64 fileSubMeshesOffset;
    public System.Int64 fileSubMeshesSize;
    public System.Int64 fileIndicesOffset;
    public System.Int64 fileIndicesSize;
    public Colossal.IO.AssetDatabase.GeometryAsset+Data+<fileAttrOffsets>e__FixedBuffer fileAttrOffsets;
    public Colossal.IO.AssetDatabase.GeometryAsset+Data+<fileAttrSize>e__FixedBuffer fileAttrSize;
    public System.Int64 fileShapesOffset;
    public System.Int64 fileShapesSize;
    public Colossal.IO.AssetDatabase.GeometryAsset+Data+<attrDataOffsets>e__FixedBuffer attrDataOffsets;
    public Colossal.IO.AssetDatabase.GeometryAsset+Data+<attrDataSize>e__FixedBuffer attrDataSize;
    public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+MeshDataOffsets> meshOffsets;
    public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+SubMeshInfo> subMeshInfos;
    public Unity.Collections.NativeArray<System.Byte> indexData;
    public Unity.Collections.NativeList<System.Byte> attrData;
    public Unity.Collections.NativeArray<System.Byte> shapeData;
    public System.UInt32 attrLoadedMask;
    public System.UInt32 attrDecompressedMask;
    public System.Boolean indicesDecompressed;
    public System.Boolean shapesDecompressed;

    public System.Boolean IsValid { get; }

    public System.Void ComputeFileOffsets(System.Int64 offset, System.Int64 fileSize);
    public System.Void Dispose();
    public System.Void ValidateHeaders();
}
```


## Fields

- `public System.Int32 meshCount`  

```csharp
public System.Int32 meshCount;
```

- `public System.UInt32 fileFlags`  

```csharp
public System.UInt32 fileFlags;
```

- `public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader> meshInfos`  

```csharp
public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader> meshInfos;
```

- `public System.Int32 shapeCount`  

```csharp
public System.Int32 shapeCount;
```

- `public System.Int64 fileSubMeshesOffset`  

```csharp
public System.Int64 fileSubMeshesOffset;
```

- `public System.Int64 fileSubMeshesSize`  

```csharp
public System.Int64 fileSubMeshesSize;
```

- `public System.Int64 fileIndicesOffset`  

```csharp
public System.Int64 fileIndicesOffset;
```

- `public System.Int64 fileIndicesSize`  

```csharp
public System.Int64 fileIndicesSize;
```

- `public Colossal.IO.AssetDatabase.GeometryAsset+Data+<fileAttrOffsets>e__FixedBuffer fileAttrOffsets`  

```csharp
public Colossal.IO.AssetDatabase.GeometryAsset+Data+<fileAttrOffsets>e__FixedBuffer fileAttrOffsets;
```

- `public Colossal.IO.AssetDatabase.GeometryAsset+Data+<fileAttrSize>e__FixedBuffer fileAttrSize`  

```csharp
public Colossal.IO.AssetDatabase.GeometryAsset+Data+<fileAttrSize>e__FixedBuffer fileAttrSize;
```

- `public System.Int64 fileShapesOffset`  

```csharp
public System.Int64 fileShapesOffset;
```

- `public System.Int64 fileShapesSize`  

```csharp
public System.Int64 fileShapesSize;
```

- `public Colossal.IO.AssetDatabase.GeometryAsset+Data+<attrDataOffsets>e__FixedBuffer attrDataOffsets`  

```csharp
public Colossal.IO.AssetDatabase.GeometryAsset+Data+<attrDataOffsets>e__FixedBuffer attrDataOffsets;
```

- `public Colossal.IO.AssetDatabase.GeometryAsset+Data+<attrDataSize>e__FixedBuffer attrDataSize`  

```csharp
public Colossal.IO.AssetDatabase.GeometryAsset+Data+<attrDataSize>e__FixedBuffer attrDataSize;
```

- `public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+MeshDataOffsets> meshOffsets`  

```csharp
public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+MeshDataOffsets> meshOffsets;
```

- `public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+SubMeshInfo> subMeshInfos`  

```csharp
public Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.GeometryAsset+SubMeshInfo> subMeshInfos;
```

- `public Unity.Collections.NativeArray<System.Byte> indexData`  

```csharp
public Unity.Collections.NativeArray<System.Byte> indexData;
```

- `public Unity.Collections.NativeList<System.Byte> attrData`  

```csharp
public Unity.Collections.NativeList<System.Byte> attrData;
```

- `public Unity.Collections.NativeArray<System.Byte> shapeData`  

```csharp
public Unity.Collections.NativeArray<System.Byte> shapeData;
```

- `public System.UInt32 attrLoadedMask`  

```csharp
public System.UInt32 attrLoadedMask;
```

- `public System.UInt32 attrDecompressedMask`  

```csharp
public System.UInt32 attrDecompressedMask;
```

- `public System.Boolean indicesDecompressed`  

```csharp
public System.Boolean indicesDecompressed;
```

- `public System.Boolean shapesDecompressed`  

```csharp
public System.Boolean shapesDecompressed;
```


## Properties

- `public System.Boolean IsValid { get }`  

```csharp
public System.Boolean IsValid { get; }
```


## Methods

- `public ComputeFileOffsets(System.Int64 offset, System.Int64 fileSize) : System.Void`  

```csharp
public System.Void ComputeFileOffsets(System.Int64 offset, System.Int64 fileSize);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ValidateHeaders() : System.Void`  

```csharp
public System.Void ValidateHeaders();
```


## Nested types

- `Colossal.IO.AssetDatabase.GeometryAsset+Data+<attrDataOffsets>e__FixedBuffer`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Data+<attrDataSize>e__FixedBuffer`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Data+<fileAttrOffsets>e__FixedBuffer`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Data+<fileAttrSize>e__FixedBuffer`  

