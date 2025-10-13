# Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct MeshInfoHeader
{
    public System.UInt64 attrFormats;
    public System.UInt32 attrDims;
    public Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader+<attrDataSizes>e__FixedBuffer attrDataSizes;
    public System.Int32 indexDataSize;
    public System.UInt32 meshFlags;
    public System.Int32 vertexCount;
    public System.Int32 indexCount;
    public System.Int32 subMeshCount;

    public UnityEngine.Rendering.VertexAttributeDescriptor CalcAttrDesc(UnityEngine.Rendering.VertexAttribute attr);
}
```


## Fields

- `public System.UInt64 attrFormats`  

```csharp
public System.UInt64 attrFormats;
```

- `public System.UInt32 attrDims`  

```csharp
public System.UInt32 attrDims;
```

- `public Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader+<attrDataSizes>e__FixedBuffer attrDataSizes`  

```csharp
public Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader+<attrDataSizes>e__FixedBuffer attrDataSizes;
```

- `public System.Int32 indexDataSize`  

```csharp
public System.Int32 indexDataSize;
```

- `public System.UInt32 meshFlags`  

```csharp
public System.UInt32 meshFlags;
```

- `public System.Int32 vertexCount`  

```csharp
public System.Int32 vertexCount;
```

- `public System.Int32 indexCount`  

```csharp
public System.Int32 indexCount;
```

- `public System.Int32 subMeshCount`  

```csharp
public System.Int32 subMeshCount;
```


## Methods

- `public CalcAttrDesc(UnityEngine.Rendering.VertexAttribute attr) : UnityEngine.Rendering.VertexAttributeDescriptor`  

```csharp
public UnityEngine.Rendering.VertexAttributeDescriptor CalcAttrDesc(UnityEngine.Rendering.VertexAttribute attr);
```


## Nested types

- `Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader+<attrDataSizes>e__FixedBuffer`  

