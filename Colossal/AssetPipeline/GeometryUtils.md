# Colossal.AssetPipeline.GeometryUtils

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class GeometryUtils
{
    public static UnityEngine.Bounds CalcBounds(Unity.Collections.NativeArray<System.Int32> indices, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices);
    public static System.Void ClassifyVertexAttribute(System.Boolean hasSkin, UnityEngine.Rendering.VertexAttributeDescriptor& attr, System.Int32& vertexSize0, System.Int32& vertexSize1, System.Int32& vertexSize2);
}
```


## Methods

- `public static CalcBounds(Unity.Collections.NativeArray<System.Int32> indices, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices) : UnityEngine.Bounds`  

```csharp
public static UnityEngine.Bounds CalcBounds(Unity.Collections.NativeArray<System.Int32> indices, Unity.Collections.NativeArray<Unity.Mathematics.float3> vertices);
```

- `public static ClassifyVertexAttribute(System.Boolean hasSkin, UnityEngine.Rendering.VertexAttributeDescriptor& attr, System.Int32& vertexSize0, System.Int32& vertexSize1, System.Int32& vertexSize2) : System.Void`  

```csharp
public static System.Void ClassifyVertexAttribute(System.Boolean hasSkin, UnityEngine.Rendering.VertexAttributeDescriptor& attr, System.Int32& vertexSize0, System.Int32& vertexSize1, System.Int32& vertexSize2);
```


