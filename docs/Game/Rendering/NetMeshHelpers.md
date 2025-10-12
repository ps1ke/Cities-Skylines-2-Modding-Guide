# Game.Rendering.NetMeshHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly Unity.Mathematics.float3 v_left`  
- `private static readonly Unity.Mathematics.float3 v_up`  
- `private static readonly Unity.Mathematics.float3 v_right`  
- `private static readonly Unity.Mathematics.float3 v_down`  
- `private static readonly Unity.Mathematics.float3 v_forward`  
- `private static readonly Unity.Mathematics.float3 v_backward`  

## Methods

- `private static AddQuad(System.Int32[] indices, System.Int32& indexIndex, System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d) : System.Void`  
- `private static AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 position, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv) : System.Void`  
- `private static AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv, Unity.Mathematics.int2 m, System.Single tx, System.Single y, System.Single tz) : System.Void`  
- `public static CacheMeshData(Colossal.IO.AssetDatabase.GeometryAsset meshData, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : Unity.Jobs.JobHandle`  
- `public static CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  
- `public static CreateDefaultEdgeMesh() : UnityEngine.Mesh`  
- `public static CreateDefaultLaneMesh() : UnityEngine.Mesh`  
- `public static CreateDefaultNodeMesh() : UnityEngine.Mesh`  
- `public static CreateDefaultRoundaboutMesh() : UnityEngine.Mesh`  
- `private static CreateMesh(System.String name, UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32[] indices) : UnityEngine.Mesh`  
- `public static UncacheMeshData(Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

## Nested types

- `Game.Rendering.NetMeshHelpers+CacheMeshDataJob`  

