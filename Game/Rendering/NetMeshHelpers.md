# Game.Rendering.NetMeshHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NetMeshHelpers
{
    private static readonly Unity.Mathematics.float3 v_left;
    private static readonly Unity.Mathematics.float3 v_up;
    private static readonly Unity.Mathematics.float3 v_right;
    private static readonly Unity.Mathematics.float3 v_down;
    private static readonly Unity.Mathematics.float3 v_forward;
    private static readonly Unity.Mathematics.float3 v_backward;

    private static System.Void AddQuad(System.Int32[] indices, System.Int32& indexIndex, System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d);
    private static System.Void AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 position, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv);
    private static System.Void AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv, Unity.Mathematics.int2 m, System.Single tx, System.Single y, System.Single tz);
    public static Unity.Jobs.JobHandle CacheMeshData(Colossal.IO.AssetDatabase.GeometryAsset meshData, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer);
    public static System.Void CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer);
    public static UnityEngine.Mesh CreateDefaultEdgeMesh();
    public static UnityEngine.Mesh CreateDefaultLaneMesh();
    public static UnityEngine.Mesh CreateDefaultNodeMesh();
    public static UnityEngine.Mesh CreateDefaultRoundaboutMesh();
    private static UnityEngine.Mesh CreateMesh(System.String name, UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32[] indices);
    public static System.Void UncacheMeshData(Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer commandBuffer);
}
```


## Fields

- `private static readonly Unity.Mathematics.float3 v_left`  

```csharp
private static readonly Unity.Mathematics.float3 v_left;
```

- `private static readonly Unity.Mathematics.float3 v_up`  

```csharp
private static readonly Unity.Mathematics.float3 v_up;
```

- `private static readonly Unity.Mathematics.float3 v_right`  

```csharp
private static readonly Unity.Mathematics.float3 v_right;
```

- `private static readonly Unity.Mathematics.float3 v_down`  

```csharp
private static readonly Unity.Mathematics.float3 v_down;
```

- `private static readonly Unity.Mathematics.float3 v_forward`  

```csharp
private static readonly Unity.Mathematics.float3 v_forward;
```

- `private static readonly Unity.Mathematics.float3 v_backward`  

```csharp
private static readonly Unity.Mathematics.float3 v_backward;
```


## Methods

- `private static AddQuad(System.Int32[] indices, System.Int32& indexIndex, System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d) : System.Void`  

```csharp
private static System.Void AddQuad(System.Int32[] indices, System.Int32& indexIndex, System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d);
```

- `private static AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 position, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv) : System.Void`  

```csharp
private static System.Void AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 position, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv);
```

- `private static AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv, Unity.Mathematics.int2 m, System.Single tx, System.Single y, System.Single tz) : System.Void`  

```csharp
private static System.Void AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv, Unity.Mathematics.int2 m, System.Single tx, System.Single y, System.Single tz);
```

- `public static CacheMeshData(Colossal.IO.AssetDatabase.GeometryAsset meshData, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : Unity.Jobs.JobHandle`  

```csharp
public static Unity.Jobs.JobHandle CacheMeshData(Colossal.IO.AssetDatabase.GeometryAsset meshData, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer);
```

- `public static CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

```csharp
public static System.Void CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer);
```

- `public static CreateDefaultEdgeMesh() : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateDefaultEdgeMesh();
```

- `public static CreateDefaultLaneMesh() : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateDefaultLaneMesh();
```

- `public static CreateDefaultNodeMesh() : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateDefaultNodeMesh();
```

- `public static CreateDefaultRoundaboutMesh() : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateDefaultRoundaboutMesh();
```

- `private static CreateMesh(System.String name, UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32[] indices) : UnityEngine.Mesh`  

```csharp
private static UnityEngine.Mesh CreateMesh(System.String name, UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32[] indices);
```

- `public static UncacheMeshData(Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

```csharp
public static System.Void UncacheMeshData(Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer commandBuffer);
```


## Nested types

- `Game.Rendering.NetMeshHelpers+CacheMeshDataJob`  

