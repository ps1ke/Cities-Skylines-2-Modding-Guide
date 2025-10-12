# Game.Rendering.ObjectMeshHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `private static AddBaseFace(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uv, System.Int32[] indices, System.Int32& vertexIndex, System.Int32& indexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent) : System.Void`  
- `private static AddBounds(Game.Rendering.ObjectMeshHelpers+TreeNode& targetNode, System.Int32& sourceSize, Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 sourceIndex) : System.Void`  
- `private static AddFace(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uv, System.Int32[] indices, System.Int32& vertexIndex, System.Int32& indexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent) : System.Void`  
- `private static AddTriangle(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, Unity.Collections.NativeArray<System.Int32> boneIndex, Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.int3 boneID, System.Int32 triangleIndex) : System.Void`  
- `private static AddTriangle(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth, Colossal.Mathematics.Triangle3 triangle, System.Int32 index) : System.Void`  
- `public static CacheMeshData(Game.Prefabs.RenderPrefab meshPrefab, Colossal.IO.AssetDatabase.GeometryAsset meshData, Unity.Entities.Entity entity, System.Int32 boneCount, System.Boolean cacheNormals, Unity.Entities.EntityCommandBuffer commandBuffer) : Unity.Jobs.JobHandle`  
- `public static CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, System.Boolean cacheNormals, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  
- `private static CalculateTreeSize(System.Int32 indexCount, Colossal.Mathematics.Bounds3 bounds, System.Int32& treeDepth, System.Int32& treeSize, Unity.Mathematics.float3& sizeFactor, Unity.Mathematics.float3& sizeOffset) : System.Void`  
- `public static CreateDefaultBaseMesh() : UnityEngine.Mesh`  
- `public static CreateDefaultMesh() : UnityEngine.Mesh`  
- `private static FillBoneData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, System.Int32 vertexOffset, Unity.Collections.NativeSlice<System.Byte> boneIdsData, System.Int32 boneIdsDim, UnityEngine.Rendering.VertexAttributeFormat boneIdsFormat, Unity.Collections.NativeSlice<System.Byte> weightsData, System.Int32 weightsDim, UnityEngine.Rendering.VertexAttributeFormat weightsFormat, Unity.Collections.NativeArray<System.Byte> indexData, UnityEngine.Rendering.IndexFormat indexFormat, System.Int32 indexOffset) : System.Void`  
- `private static FillIndices(Game.Rendering.ObjectMeshHelpers+BoneData boneData, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<System.Int32> sourceIndices, Unity.Collections.NativeArray<System.Int32> targetIndices, System.Int32 bone) : System.Void`  
- `private static FillIndices(Game.Rendering.ObjectMeshHelpers+BoneData boneData, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<System.UInt16> sourceIndices, Unity.Collections.NativeArray<System.Int32> targetIndices, System.Int32 bone) : System.Void`  
- `private static FillMeshData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> sourceNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshNode> targetNodes, Unity.Collections.NativeArray<System.Int32> sourceIndices, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> targetIndices, System.Int32 treeDepth, System.Int32* depthOffsets) : System.Void`  
- `private static FillMeshData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> sourceNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshNode> targetNodes, Unity.Collections.NativeArray<System.UInt16> sourceIndices, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> targetIndices, System.Int32 treeDepth, System.Int32* depthOffsets) : System.Void`  
- `private static FillTreeNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, Unity.Collections.NativeArray<System.Int32> indices, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth) : System.Void`  
- `private static FillTreeNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, Unity.Collections.NativeArray<System.UInt16> indices, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth) : System.Void`  
- `private static InitializeBones(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, System.Int32 indexCount) : System.Void`  
- `private static InitializeTree(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 treeSize) : System.Void`  
- `public static UncacheMeshData(Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  
- `private static UpdateNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 treeDepth, System.Int32* depthOffsets) : System.Void`  

## Nested types

- `Game.Rendering.ObjectMeshHelpers+TreeNode`  
- `Game.Rendering.ObjectMeshHelpers+CacheMeshDataJob`  
- `Game.Rendering.ObjectMeshHelpers+CacheProceduralMeshDataJob`  
- `Game.Rendering.ObjectMeshHelpers+BoneData`  

