# Colossal.AssetPipeline.Native.NativeModelImport

**Assembly:** `Colossal.AssetPipeline.Native`  
**Namespace:** `Colossal.AssetPipeline.Native`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static AddMeshSubMesh(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc& desc) : System.Void`  
- `public static AddMeshVertexAttribute(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+AttributeData& desc) : System.Void`  
- `public static CreateMesh(System.Int32 vertexCount) : System.IntPtr`  
- `public static Free(System.IntPtr scene) : System.Void`  
- `public static FreeMesh(System.IntPtr mesh) : System.Void`  
- `public static GetErrorMessage(System.IntPtr scene) : System.IntPtr`  
- `public static GetMeshBlendShape(System.IntPtr mesh, System.Int32 shapeIndex, Colossal.AssetPipeline.Native.NativeModelImport+BlendShapeDelta* deltas) : System.Void`  
- `public static GetMeshBoneBindpose(System.IntPtr mesh, System.Int32 boneIndex, UnityEngine.Matrix4x4& bindPose) : System.Void`  
- `public static GetMeshBoneID(System.IntPtr mesh, System.Int32 boneIndex) : System.Int32`  
- `public static GetMeshBoneName(System.IntPtr mesh, System.Int32 boneIndex) : System.IntPtr`  
- `public static GetMeshBoneTransform(System.IntPtr mesh, System.Int32 boneIndex, UnityEngine.Vector3& localPos, UnityEngine.Quaternion& localRot, UnityEngine.Vector3& localScale, System.Int32& parentIndex) : System.Void`  
- `public static GetMeshCount(System.IntPtr scene) : System.Int32`  
- `public static GetMeshDesc(System.IntPtr mesh, Colossal.AssetPipeline.Native.NativeModelImport+MeshDesc& desc) : System.Void`  
- `public static GetMeshIndexBufferPtr(System.IntPtr mesh) : System.IntPtr`  
- `public static GetMeshPtr(System.IntPtr scene, System.Int32 meshIndex) : System.IntPtr`  
- `public static GetMeshSubMesh(System.IntPtr mesh, System.Int32 subMeshIndex, Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc& desc) : System.Void`  
- `public static GetMeshTransform(System.IntPtr mesh, UnityEngine.Matrix4x4& transform) : System.Void`  
- `public static GetMeshVertexAttribute(System.IntPtr mesh, System.Int32 attrIndex, Colossal.AssetPipeline.Native.NativeModelImport+AttributeData& desc) : System.Void`  
- `public static GetNodeAnimDesc(System.IntPtr scene, System.Int32 nodeIndex, Colossal.AssetPipeline.Native.NativeModelImport+AnimDesc& desc) : System.Void`  
- `public static GetNodeAnimSamples(System.IntPtr scene, System.Int32 nodeIndex, Colossal.AssetPipeline.Native.NativeModelImport+AnimTransformSample* samples) : System.Void`  
- `public static GetSceneAnimDesc(System.IntPtr scene, Colossal.AssetPipeline.Native.NativeModelImport+SceneAnimDesc& desc) : System.Void`  
- `public static LoadFromMemory(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeModelImport+ImportSettings& settings) : System.IntPtr`  
- `public static MeshComputeTangentSpace(System.IntPtr mesh) : System.Void`  
- `public static MeshGenerateAdjacency(System.IntPtr mesh, System.IntPtr targetAdjacencyBuffer) : System.Void`  
- `public static MeshOptimizeForGPU(System.IntPtr mesh, System.IntPtr outVertexRemap) : System.Void`  
- `public static MeshSimplify(System.IntPtr mesh, System.Int32 targetIndexCount, System.Single targetRelError, System.IntPtr attributeImportance, System.Int32 sloppy, System.IntPtr targetIndexBuffer) : System.Int32`  
- `public static MeshWeldVertices(System.IntPtr mesh, System.IntPtr outVertexRemap) : System.Void`  
- `public static SetMeshIndices(System.IntPtr mesh, System.Int32 indexCount, System.IntPtr indexBufferUInt32) : System.Void`  

## Nested types

- `Colossal.AssetPipeline.Native.NativeModelImport+ImportSettings`  
- `Colossal.AssetPipeline.Native.NativeModelImport+AttributeData`  
- `Colossal.AssetPipeline.Native.NativeModelImport+SubMeshDesc`  
- `Colossal.AssetPipeline.Native.NativeModelImport+MeshDesc`  
- `Colossal.AssetPipeline.Native.NativeModelImport+SceneAnimDesc`  
- `Colossal.AssetPipeline.Native.NativeModelImport+AnimDesc`  
- `Colossal.AssetPipeline.Native.NativeModelImport+AnimTransformSample`  
- `Colossal.AssetPipeline.Native.NativeModelImport+BlendShapeDelta`  

