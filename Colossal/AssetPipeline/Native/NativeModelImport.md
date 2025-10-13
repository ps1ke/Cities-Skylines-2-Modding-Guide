# Colossal.AssetPipeline.Native.NativeModelImport

**Assembly:** `Colossal.AssetPipeline.Native`  
**Namespace:** `Colossal.AssetPipeline.Native`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NativeModelImport
{
    public static System.Void AddMeshSubMesh(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc& desc);
    public static System.Void AddMeshVertexAttribute(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+AttributeData& desc);
    public static System.IntPtr CreateMesh(System.Int32 vertexCount);
    public static System.Void Free(System.IntPtr scene);
    public static System.Void FreeMesh(System.IntPtr mesh);
    public static System.IntPtr GetErrorMessage(System.IntPtr scene);
    public static System.Void GetMeshBlendShape(System.IntPtr mesh, System.Int32 shapeIndex, Colossal.AssetPipeline.Native.NativeModelImport+BlendShapeDelta* deltas);
    public static System.Void GetMeshBoneBindpose(System.IntPtr mesh, System.Int32 boneIndex, UnityEngine.Matrix4x4& bindPose);
    public static System.Int32 GetMeshBoneID(System.IntPtr mesh, System.Int32 boneIndex);
    public static System.IntPtr GetMeshBoneName(System.IntPtr mesh, System.Int32 boneIndex);
    public static System.Void GetMeshBoneTransform(System.IntPtr mesh, System.Int32 boneIndex, UnityEngine.Vector3& localPos, UnityEngine.Quaternion& localRot, UnityEngine.Vector3& localScale, System.Int32& parentIndex);
    public static System.Int32 GetMeshCount(System.IntPtr scene);
    public static System.Void GetMeshDesc(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+MeshDesc& desc);
    public static System.IntPtr GetMeshIndexBufferPtr(System.IntPtr mesh);
    public static System.IntPtr GetMeshPtr(System.IntPtr scene, System.Int32 meshIndex);
    public static System.Void GetMeshSubMesh(System.IntPtr mesh, System.Int32 subMeshIndex, Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc& desc);
    public static System.Void GetMeshTransform(System.IntPtr mesh, UnityEngine.Matrix4x4& transform);
    public static System.Void GetMeshVertexAttribute(System.IntPtr mesh, System.Int32 attrIndex, Colossal.AssetPipeline.Native.NativeModelImport+AttributeData& desc);
    public static System.Void GetNodeAnimDesc(System.IntPtr scene, System.Int32 nodeIndex, Colossal.AssetPipeline.Native.NativeModelImport+AnimDesc& desc);
    public static System.Void GetNodeAnimSamples(System.IntPtr scene, System.Int32 nodeIndex, Colossal.AssetPipeline.Native.NativeModelImport+AnimTransformSample* samples);
    public static System.Void GetSceneAnimDesc(System.IntPtr scene, Colossal.AssetPipeline.Native.NativeModelImport+SceneAnimDesc& desc);
    public static System.IntPtr LoadFromMemory(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeModelImport+ImportSettings& settings);
    public static System.Void MeshComputeTangentSpace(System.IntPtr mesh);
    public static System.Void MeshGenerateAdjacency(System.IntPtr mesh, System.IntPtr targetAdjacencyBuffer);
    public static System.Void MeshOptimizeForGPU(System.IntPtr mesh, System.IntPtr outVertexRemap);
    public static System.Int32 MeshSimplify(System.IntPtr mesh, System.Int32 targetIndexCount, System.Single targetRelError, System.IntPtr attributeImportance, System.Int32 sloppy, System.IntPtr targetIndexBuffer);
    public static System.Void MeshWeldVertices(System.IntPtr mesh, System.IntPtr outVertexRemap);
    public static System.Void SetMeshIndices(System.IntPtr mesh, System.Int32 indexCount, System.IntPtr indexBufferUInt32);
}
```


## Methods

- `public static AddMeshSubMesh(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc& desc) : System.Void`  

```csharp
public static System.Void AddMeshSubMesh(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc& desc);
```

- `public static AddMeshVertexAttribute(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+AttributeData& desc) : System.Void`  

```csharp
public static System.Void AddMeshVertexAttribute(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+AttributeData& desc);
```

- `public static CreateMesh(System.Int32 vertexCount) : System.IntPtr`  

```csharp
public static System.IntPtr CreateMesh(System.Int32 vertexCount);
```

- `public static Free(System.IntPtr scene) : System.Void`  

```csharp
public static System.Void Free(System.IntPtr scene);
```

- `public static FreeMesh(System.IntPtr mesh) : System.Void`  

```csharp
public static System.Void FreeMesh(System.IntPtr mesh);
```

- `public static GetErrorMessage(System.IntPtr scene) : System.IntPtr`  

```csharp
public static System.IntPtr GetErrorMessage(System.IntPtr scene);
```

- `public static GetMeshBlendShape(System.IntPtr mesh, System.Int32 shapeIndex, Colossal.AssetPipeline.Native.NativeModelImport+BlendShapeDelta* deltas) : System.Void`  

```csharp
public static System.Void GetMeshBlendShape(System.IntPtr mesh, System.Int32 shapeIndex, Colossal.AssetPipeline.Native.NativeModelImport+BlendShapeDelta* deltas);
```

- `public static GetMeshBoneBindpose(System.IntPtr mesh, System.Int32 boneIndex, UnityEngine.Matrix4x4& bindPose) : System.Void`  

```csharp
public static System.Void GetMeshBoneBindpose(System.IntPtr mesh, System.Int32 boneIndex, UnityEngine.Matrix4x4& bindPose);
```

- `public static GetMeshBoneID(System.IntPtr mesh, System.Int32 boneIndex) : System.Int32`  

```csharp
public static System.Int32 GetMeshBoneID(System.IntPtr mesh, System.Int32 boneIndex);
```

- `public static GetMeshBoneName(System.IntPtr mesh, System.Int32 boneIndex) : System.IntPtr`  

```csharp
public static System.IntPtr GetMeshBoneName(System.IntPtr mesh, System.Int32 boneIndex);
```

- `public static GetMeshBoneTransform(System.IntPtr mesh, System.Int32 boneIndex, UnityEngine.Vector3& localPos, UnityEngine.Quaternion& localRot, UnityEngine.Vector3& localScale, System.Int32& parentIndex) : System.Void`  

```csharp
public static System.Void GetMeshBoneTransform(System.IntPtr mesh, System.Int32 boneIndex, UnityEngine.Vector3& localPos, UnityEngine.Quaternion& localRot, UnityEngine.Vector3& localScale, System.Int32& parentIndex);
```

- `public static GetMeshCount(System.IntPtr scene) : System.Int32`  

```csharp
public static System.Int32 GetMeshCount(System.IntPtr scene);
```

- `public static GetMeshDesc(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+MeshDesc& desc) : System.Void`  

```csharp
public static System.Void GetMeshDesc(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+MeshDesc& desc);
```

- `public static GetMeshIndexBufferPtr(System.IntPtr mesh) : System.IntPtr`  

```csharp
public static System.IntPtr GetMeshIndexBufferPtr(System.IntPtr mesh);
```

- `public static GetMeshPtr(System.IntPtr scene, System.Int32 meshIndex) : System.IntPtr`  

```csharp
public static System.IntPtr GetMeshPtr(System.IntPtr scene, System.Int32 meshIndex);
```

- `public static GetMeshSubMesh(System.IntPtr mesh, System.Int32 subMeshIndex, Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc& desc) : System.Void`  

```csharp
public static System.Void GetMeshSubMesh(System.IntPtr mesh, System.Int32 subMeshIndex, Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc& desc);
```

- `public static GetMeshTransform(System.IntPtr mesh, UnityEngine.Matrix4x4& transform) : System.Void`  

```csharp
public static System.Void GetMeshTransform(System.IntPtr mesh, UnityEngine.Matrix4x4& transform);
```

- `public static GetMeshVertexAttribute(System.IntPtr mesh, System.Int32 attrIndex, Colossal.AssetPipeline.Native.NativeModelImport+AttributeData& desc) : System.Void`  

```csharp
public static System.Void GetMeshVertexAttribute(System.IntPtr mesh, System.Int32 attrIndex, Colossal.AssetPipeline.Native.NativeModelImport+AttributeData& desc);
```

- `public static GetNodeAnimDesc(System.IntPtr scene, System.Int32 nodeIndex, Colossal.AssetPipeline.Native.NativeModelImport+AnimDesc& desc) : System.Void`  

```csharp
public static System.Void GetNodeAnimDesc(System.IntPtr scene, System.Int32 nodeIndex, Colossal.AssetPipeline.Native.NativeModelImport+AnimDesc& desc);
```

- `public static GetNodeAnimSamples(System.IntPtr scene, System.Int32 nodeIndex, Colossal.AssetPipeline.Native.NativeModelImport+AnimTransformSample* samples) : System.Void`  

```csharp
public static System.Void GetNodeAnimSamples(System.IntPtr scene, System.Int32 nodeIndex, Colossal.AssetPipeline.Native.NativeModelImport+AnimTransformSample* samples);
```

- `public static GetSceneAnimDesc(System.IntPtr scene, Colossal.AssetPipeline.Native.NativeModelImport+SceneAnimDesc& desc) : System.Void`  

```csharp
public static System.Void GetSceneAnimDesc(System.IntPtr scene, Colossal.AssetPipeline.Native.NativeModelImport+SceneAnimDesc& desc);
```

- `public static LoadFromMemory(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeModelImport+ImportSettings& settings) : System.IntPtr`  

```csharp
public static System.IntPtr LoadFromMemory(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeModelImport+ImportSettings& settings);
```

- `public static MeshComputeTangentSpace(System.IntPtr mesh) : System.Void`  

```csharp
public static System.Void MeshComputeTangentSpace(System.IntPtr mesh);
```

- `public static MeshGenerateAdjacency(System.IntPtr mesh, System.IntPtr targetAdjacencyBuffer) : System.Void`  

```csharp
public static System.Void MeshGenerateAdjacency(System.IntPtr mesh, System.IntPtr targetAdjacencyBuffer);
```

- `public static MeshOptimizeForGPU(System.IntPtr mesh, System.IntPtr outVertexRemap) : System.Void`  

```csharp
public static System.Void MeshOptimizeForGPU(System.IntPtr mesh, System.IntPtr outVertexRemap);
```

- `public static MeshSimplify(System.IntPtr mesh, System.Int32 targetIndexCount, System.Single targetRelError, System.IntPtr attributeImportance, System.Int32 sloppy, System.IntPtr targetIndexBuffer) : System.Int32`  

```csharp
public static System.Int32 MeshSimplify(System.IntPtr mesh, System.Int32 targetIndexCount, System.Single targetRelError, System.IntPtr attributeImportance, System.Int32 sloppy, System.IntPtr targetIndexBuffer);
```

- `public static MeshWeldVertices(System.IntPtr mesh, System.IntPtr outVertexRemap) : System.Void`  

```csharp
public static System.Void MeshWeldVertices(System.IntPtr mesh, System.IntPtr outVertexRemap);
```

- `public static SetMeshIndices(System.IntPtr mesh, System.Int32 indexCount, System.IntPtr indexBufferUInt32) : System.Void`  

```csharp
public static System.Void SetMeshIndices(System.IntPtr mesh, System.Int32 indexCount, System.IntPtr indexBufferUInt32);
```


## Nested types

- `Colossal.AssetPipeline.Native.NativeModelImport+ImportSettings`  
- `Colossal.AssetPipeline.Native.NativeModelImport+AttributeData`  
- `Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc`  
- `Colossal.AssetPipeline.Native.NativeModelImport+MeshDesc`  
- `Colossal.AssetPipeline.Native.NativeModelImport+SceneAnimDesc`  
- `Colossal.AssetPipeline.Native.NativeModelImport+AnimDesc`  
- `Colossal.AssetPipeline.Native.NativeModelImport+AnimTransformSample`  
- `Colossal.AssetPipeline.Native.NativeModelImport+BlendShapeDelta`  

