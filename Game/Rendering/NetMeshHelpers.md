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
private static void AddQuad(int[] indices, ref int indexIndex, int a, int b, int c, int d)
	{
		indices[indexIndex++] = a;
		indices[indexIndex++] = b;
		indices[indexIndex++] = c;
		indices[indexIndex++] = c;
		indices[indexIndex++] = d;
		indices[indexIndex++] = a;
	}
```

- `private static AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 position, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv) : System.Void`  

```csharp
private static void AddVertex(Vector3[] vertices, Vector3[] normals, Vector4[] tangents, Color32[] colors, Vector4[] uvs, ref int vertexIndex, float3 normal, float3 tangent, float2 uv, int2 m, float tx, float y, float tz)
	{
		vertices[vertexIndex] = new Vector3(tx, y, tz);
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		colors[vertexIndex] = new Color32((byte)m.x, (byte)m.y, 0, 0);
		uvs[vertexIndex] = new Vector4(uv.x, uv.y, 0.5f, 0f);
		vertexIndex++;
	}
```

- `private static AddVertex(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32& vertexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent, Unity.Mathematics.float2 uv, Unity.Mathematics.int2 m, System.Single tx, System.Single y, System.Single tz) : System.Void`  

```csharp
private static void AddVertex(Vector3[] vertices, Vector3[] normals, Vector4[] tangents, Color32[] colors, Vector4[] uvs, ref int vertexIndex, float3 normal, float3 tangent, float2 uv, int2 m, float tx, float y, float tz)
	{
		vertices[vertexIndex] = new Vector3(tx, y, tz);
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		colors[vertexIndex] = new Color32((byte)m.x, (byte)m.y, 0, 0);
		uvs[vertexIndex] = new Vector4(uv.x, uv.y, 0.5f, 0f);
		vertexIndex++;
	}
```

- `public static CacheMeshData(Colossal.IO.AssetDatabase.GeometryAsset meshData, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : Unity.Jobs.JobHandle`  

```csharp
public static void CacheMeshData(Mesh mesh, Entity entity, EntityManager entityManager, EntityCommandBuffer commandBuffer)
	{
		DynamicBuffer<MeshVertex> dynamicBuffer = commandBuffer.AddBuffer<MeshVertex>(entity);
		DynamicBuffer<MeshNormal> dynamicBuffer2 = commandBuffer.AddBuffer<MeshNormal>(entity);
		DynamicBuffer<MeshTangent> dynamicBuffer3 = commandBuffer.AddBuffer<MeshTangent>(entity);
		DynamicBuffer<MeshUV0> dynamicBuffer4 = commandBuffer.AddBuffer<MeshUV0>(entity);
		DynamicBuffer<MeshIndex> dynamicBuffer5 = commandBuffer.AddBuffer<MeshIndex>(entity);
		DynamicBuffer<MeshMaterial> buffer = entityManager.GetBuffer<MeshMaterial>(entity);
		Mesh.MeshDataArray meshDataArray = Mesh.AcquireReadOnlyMeshData(mesh);
		Mesh.MeshData meshData = meshDataArray[0];
		int num = 0;
		int subMeshCount = meshData.subMeshCount;
		for (int i = 0; i < subMeshCount; i++)
		{
			num += meshData.GetSubMesh(i).indexCount;
		}
		dynamicBuffer.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer2.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer3.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer4.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer5.ResizeUninitialized(num);
		meshData.GetVertices(dynamicBuffer.AsNativeArray().Reinterpret<Vector3>());
		meshData.GetNormals(dynamicBuffer2.AsNativeArray().Reinterpret<Vector3>());
		meshData.GetTangents(dynamicBuffer3.AsNativeArray().Reinterpret<Vector4>());
		meshData.GetUVs(0, dynamicBuffer4.AsNativeArray().Reinterpret<Vector2>());
		num = 0;
		for (int j = 0; j < subMeshCount; j++)
		{
			SubMeshDescriptor subMesh = meshData.GetSubMesh(j);
			meshData.GetIndices(dynamicBuffer5.AsNativeArray().GetSubArray(num, subMesh.indexCount).Reinterpret<int>(), j);
			MeshMaterial value = buffer[j];
			value.m_StartIndex = subMesh.indexStart;
			value.m_IndexCount = subMesh.indexCount;
			value.m_StartVertex = subMesh.firstVertex;
			value.m_VertexCount = subMesh.vertexCount;
			buffer[j] = value;
			num += subMesh.indexCount;
		}
		meshDataArray.Dispose();
	}
```

- `public static CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

```csharp
public static void CacheMeshData(Mesh mesh, Entity entity, EntityManager entityManager, EntityCommandBuffer commandBuffer)
	{
		DynamicBuffer<MeshVertex> dynamicBuffer = commandBuffer.AddBuffer<MeshVertex>(entity);
		DynamicBuffer<MeshNormal> dynamicBuffer2 = commandBuffer.AddBuffer<MeshNormal>(entity);
		DynamicBuffer<MeshTangent> dynamicBuffer3 = commandBuffer.AddBuffer<MeshTangent>(entity);
		DynamicBuffer<MeshUV0> dynamicBuffer4 = commandBuffer.AddBuffer<MeshUV0>(entity);
		DynamicBuffer<MeshIndex> dynamicBuffer5 = commandBuffer.AddBuffer<MeshIndex>(entity);
		DynamicBuffer<MeshMaterial> buffer = entityManager.GetBuffer<MeshMaterial>(entity);
		Mesh.MeshDataArray meshDataArray = Mesh.AcquireReadOnlyMeshData(mesh);
		Mesh.MeshData meshData = meshDataArray[0];
		int num = 0;
		int subMeshCount = meshData.subMeshCount;
		for (int i = 0; i < subMeshCount; i++)
		{
			num += meshData.GetSubMesh(i).indexCount;
		}
		dynamicBuffer.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer2.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer3.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer4.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer5.ResizeUninitialized(num);
		meshData.GetVertices(dynamicBuffer.AsNativeArray().Reinterpret<Vector3>());
		meshData.GetNormals(dynamicBuffer2.AsNativeArray().Reinterpret<Vector3>());
		meshData.GetTangents(dynamicBuffer3.AsNativeArray().Reinterpret<Vector4>());
		meshData.GetUVs(0, dynamicBuffer4.AsNativeArray().Reinterpret<Vector2>());
		num = 0;
		for (int j = 0; j < subMeshCount; j++)
		{
			SubMeshDescriptor subMesh = meshData.GetSubMesh(j);
			meshData.GetIndices(dynamicBuffer5.AsNativeArray().GetSubArray(num, subMesh.indexCount).Reinterpret<int>(), j);
			MeshMaterial value = buffer[j];
			value.m_StartIndex = subMesh.indexStart;
			value.m_IndexCount = subMesh.indexCount;
			value.m_StartVertex = subMesh.firstVertex;
			value.m_VertexCount = subMesh.vertexCount;
			buffer[j] = value;
			num += subMesh.indexCount;
		}
		meshDataArray.Dispose();
	}
```

- `public static CreateDefaultEdgeMesh() : UnityEngine.Mesh`  

```csharp
public static Mesh CreateDefaultEdgeMesh()
	{
		int num = 4;
		int num2 = num * 8 + 16;
		int num3 = num * 24 + 12;
		Vector3[] vertices = new Vector3[num2];
		Vector3[] normals = new Vector3[num2];
		Vector4[] tangents = new Vector4[num2];
		Color32[] colors = new Color32[num2];
		Vector4[] uvs = new Vector4[num2];
		int[] indices = new int[num3];
		int vertexIndex = 0;
		int indexIndex = 0;
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0f, -2f), new int2(0, 2), 0f, -2f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0f, -1f), new int2(0, 2), 0f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(1f, -1f), new int2(0, 2), 1f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(1f, -2f), new int2(0, 2), 1f, -2f, 0f);
		AddQuad(indices, ref indexIndex, vertexIndex - 4, vertexIndex - 3, vertexIndex - 2, vertexIndex - 1);
		for (int i = 0; i <= num; i++)
		{
			int2 m = new int2(0, 2);
			float num4 = (float)i / ((float)num * 0.5f);
			float y = num4 - 3f;
			if (i >= num >> 1)
			{
				m += 1;
				num4 -= 1f;
			}
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_left, v_up, new float2(0f, y), m, 0f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_left, v_up, new float2(1f, y), m, 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(0f, y), m, 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(1f, y), m, 1f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_right, v_down, new float2(0f, y), m, 1f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_right, v_down, new float2(1f, y), m, 1f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(0f, y), m, 1f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(1f, y), m, 0f, -2f, num4);
			if (i != 0)
			{
				AddQuad(indices, ref indexIndex, vertexIndex - 16, vertexIndex - 8, vertexIndex - 7, vertexIndex - 15);
				AddQuad(indices, ref indexIndex, vertexIndex - 14, vertexIndex - 6, vertexIndex - 5, vertexIndex - 13);
				AddQuad(indices, ref indexIndex, vertexIndex - 12, vertexIndex - 4, vertexIndex - 3, vertexIndex - 11);
				AddQuad(indices, ref indexIndex, vertexIndex - 10, vertexIndex - 2, vertexIndex - 1, vertexIndex - 9);
			}
		}
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0f, -2f), new int2(1, 3), 1f, -2f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0f, -1f), new int2(1, 3), 1f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(1f, -1f), new int2(1, 3), 0f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(1f, -2f), new int2(1, 3), 0f, -2f, 1f);
		AddQuad(indices, ref indexIndex, vertexIndex - 4, vertexIndex - 3, vertexIndex - 2, vertexIndex - 1);
		return CreateMesh("Default edge", vertices, normals, tangents, colors, uvs, indices);
	}
```

- `public static CreateDefaultLaneMesh() : UnityEngine.Mesh`  

```csharp
public static Mesh CreateDefaultLaneMesh()
	{
		int num = 4;
		int num2 = num * 8 + 16;
		int num3 = num * 24 + 12;
		Vector3[] vertices = new Vector3[num2];
		Vector3[] normals = new Vector3[num2];
		Vector4[] tangents = new Vector4[num2];
		Vector2[] array = new Vector2[num2];
		int[] array2 = new int[num3];
		int vertexIndex = 0;
		int indexIndex = 0;
		AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(-1f, -1f, -1f), v_backward, v_right, new float2(0f, 0f));
		AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(-1f, 1f, -1f), v_backward, v_right, new float2(0f, 1f));
		AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(1f, 1f, -1f), v_backward, v_right, new float2(1f, 1f));
		AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(1f, -1f, -1f), v_backward, v_right, new float2(1f, 0f));
		AddQuad(array2, ref indexIndex, vertexIndex - 4, vertexIndex - 3, vertexIndex - 2, vertexIndex - 1);
		for (int i = 0; i <= num; i++)
		{
			float num4 = (float)i / (float)num;
			float z = num4 * 2f - 1f;
			AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(-1f, -1f, z), v_left, v_up, new float2(0f, num4));
			AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(-1f, 1f, z), v_left, v_up, new float2(1f, num4));
			AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(-1f, 1f, z), v_up, v_right, new float2(0f, num4));
			AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(1f, 1f, z), v_up, v_right, new float2(1f, num4));
			AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(1f, 1f, z), v_right, v_down, new float2(0f, num4));
			AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(1f, -1f, z), v_right, v_down, new float2(1f, num4));
			AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(1f, -1f, z), v_down, v_left, new float2(0f, num4));
			AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(-1f, -1f, z), v_down, v_left, new float2(1f, num4));
			if (i != 0)
			{
				AddQuad(array2, ref indexIndex, vertexIndex - 16, vertexIndex - 8, vertexIndex - 7, vertexIndex - 15);
				AddQuad(array2, ref indexIndex, vertexIndex - 14, vertexIndex - 6, vertexIndex - 5, vertexIndex - 13);
				AddQuad(array2, ref indexIndex, vertexIndex - 12, vertexIndex - 4, vertexIndex - 3, vertexIndex - 11);
				AddQuad(array2, ref indexIndex, vertexIndex - 10, vertexIndex - 2, vertexIndex - 1, vertexIndex - 9);
			}
		}
		AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(1f, -1f, 1f), v_forward, v_left, new float2(0f, 0f));
		AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(1f, 1f, 1f), v_forward, v_left, new float2(0f, 1f));
		AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(-1f, 1f, 1f), v_forward, v_left, new float2(1f, 1f));
		AddVertex(vertices, normals, tangents, array, ref vertexIndex, new float3(-1f, -1f, 1f), v_forward, v_left, new float2(1f, 0f));
		AddQuad(array2, ref indexIndex, vertexIndex - 4, vertexIndex - 3, vertexIndex - 2, vertexIndex - 1);
		return new Mesh
		{
			name = "Default lane",
			vertices = vertices,
			normals = normals,
			tangents = tangents,
			uv = array,
			triangles = array2
		};
	}
```

- `public static CreateDefaultNodeMesh() : UnityEngine.Mesh`  

```csharp
public static Mesh CreateDefaultNodeMesh()
	{
		int num = 2;
		int num2 = num * 14 + 34;
		int num3 = num * 60 + 48;
		Vector3[] vertices = new Vector3[num2];
		Vector3[] normals = new Vector3[num2];
		Vector4[] tangents = new Vector4[num2];
		Color32[] colors = new Color32[num2];
		Vector4[] uvs = new Vector4[num2];
		int[] indices = new int[num3];
		int vertexIndex = 0;
		int indexIndex = 0;
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0f, -2f), new int2(0, 2), 0f, -2f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0f, -1f), new int2(0, 2), 0f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0.25f, -1f), new int2(0, 2), 1f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0.5f, -1f), new int2(4, 0), 0f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0.75f, -1f), new int2(1, 3), 0f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(1f, -1f), new int2(1, 3), 1f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(1f, -2f), new int2(1, 3), 1f, -2f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0.75f, -2f), new int2(1, 3), 0f, -2f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0.5f, -2f), new int2(4, 0), 0f, -2f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0.25f, -2f), new int2(0, 2), 1f, -2f, 0f);
		AddQuad(indices, ref indexIndex, vertexIndex - 10, vertexIndex - 9, vertexIndex - 8, vertexIndex - 1);
		AddQuad(indices, ref indexIndex, vertexIndex - 1, vertexIndex - 8, vertexIndex - 7, vertexIndex - 2);
		AddQuad(indices, ref indexIndex, vertexIndex - 2, vertexIndex - 7, vertexIndex - 6, vertexIndex - 3);
		AddQuad(indices, ref indexIndex, vertexIndex - 3, vertexIndex - 6, vertexIndex - 5, vertexIndex - 4);
		for (int i = 0; i <= num; i++)
		{
			float num4 = (float)i / (float)num;
			float y = num4 - 2f;
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_left, v_up, new float2(0f, y), new int2(0, 2), 0f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_left, v_up, new float2(1f, y), new int2(0, 2), 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(0f, y), new int2(0, 2), 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(0.25f, y), new int2(0, 2), 1f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(0.5f, y), new int2(4, 0), 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(0.75f, y), new int2(1, 3), 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(1f, y), new int2(1, 3), 1f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_right, v_down, new float2(0f, y), new int2(1, 3), 1f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_right, v_down, new float2(1f, y), new int2(1, 3), 1f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(0f, y), new int2(1, 3), 1f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(0.25f, y), new int2(1, 3), 0f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(0.5f, y), new int2(4, 0), 0f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(0.75f, y), new int2(0, 2), 1f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(1f, y), new int2(0, 2), 0f, -2f, num4);
			if (i != 0)
			{
				AddQuad(indices, ref indexIndex, vertexIndex - 28, vertexIndex - 14, vertexIndex - 13, vertexIndex - 27);
				AddQuad(indices, ref indexIndex, vertexIndex - 26, vertexIndex - 12, vertexIndex - 11, vertexIndex - 25);
				AddQuad(indices, ref indexIndex, vertexIndex - 25, vertexIndex - 11, vertexIndex - 10, vertexIndex - 24);
				AddQuad(indices, ref indexIndex, vertexIndex - 24, vertexIndex - 10, vertexIndex - 9, vertexIndex - 23);
				AddQuad(indices, ref indexIndex, vertexIndex - 23, vertexIndex - 9, vertexIndex - 8, vertexIndex - 22);
				AddQuad(indices, ref indexIndex, vertexIndex - 21, vertexIndex - 7, vertexIndex - 6, vertexIndex - 20);
				AddQuad(indices, ref indexIndex, vertexIndex - 19, vertexIndex - 5, vertexIndex - 4, vertexIndex - 18);
				AddQuad(indices, ref indexIndex, vertexIndex - 18, vertexIndex - 4, vertexIndex - 3, vertexIndex - 17);
				AddQuad(indices, ref indexIndex, vertexIndex - 17, vertexIndex - 3, vertexIndex - 2, vertexIndex - 16);
				AddQuad(indices, ref indexIndex, vertexIndex - 16, vertexIndex - 2, vertexIndex - 1, vertexIndex - 15);
			}
		}
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0f, -2f), new int2(1, 3), 1f, -2f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0f, -1f), new int2(1, 3), 1f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0.25f, -1f), new int2(1, 3), 0f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0.5f, -1f), new int2(4, 0), 0f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0.75f, -1f), new int2(0, 2), 1f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(1f, -1f), new int2(0, 2), 0f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(1f, -2f), new int2(0, 2), 0f, -2f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0.75f, -2f), new int2(0, 2), 1f, -2f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0.5f, -2f), new int2(4, 0), 0f, -2f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0.25f, -2f), new int2(1, 3), 0f, -2f, 1f);
		AddQuad(indices, ref indexIndex, vertexIndex - 10, vertexIndex - 9, vertexIndex - 8, vertexIndex - 1);
		AddQuad(indices, ref indexIndex, vertexIndex - 1, vertexIndex - 8, vertexIndex - 7, vertexIndex - 2);
		AddQuad(indices, ref indexIndex, vertexIndex - 2, vertexIndex - 7, vertexIndex - 6, vertexIndex - 3);
		AddQuad(indices, ref indexIndex, vertexIndex - 3, vertexIndex - 6, vertexIndex - 5, vertexIndex - 4);
		return CreateMesh("Default node", vertices, normals, tangents, colors, uvs, indices);
	}
```

- `public static CreateDefaultRoundaboutMesh() : UnityEngine.Mesh`  

```csharp
public static Mesh CreateDefaultRoundaboutMesh()
	{
		int num = 4;
		int num2 = num * 10 + 22;
		int num3 = num * 36 + 24;
		Vector3[] vertices = new Vector3[num2];
		Vector3[] normals = new Vector3[num2];
		Vector4[] tangents = new Vector4[num2];
		Color32[] colors = new Color32[num2];
		Vector4[] uvs = new Vector4[num2];
		int[] indices = new int[num3];
		int vertexIndex = 0;
		int indexIndex = 0;
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0f, -2f), new int2(0, 4), 0f, -2f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0f, -1f), new int2(0, 4), 0f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0.5f, -1f), new int2(4, 2), 0f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(1f, -1f), new int2(4, 2), 1f, 0f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(1f, -2f), new int2(4, 2), 1f, -2f, 0f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_backward, v_right, new float2(0.5f, -2f), new int2(4, 2), 0f, -2f, 0f);
		AddQuad(indices, ref indexIndex, vertexIndex - 6, vertexIndex - 5, vertexIndex - 4, vertexIndex - 1);
		AddQuad(indices, ref indexIndex, vertexIndex - 1, vertexIndex - 4, vertexIndex - 3, vertexIndex - 2);
		for (int i = 0; i <= num; i++)
		{
			int3 @int = new int3(0, 4, 2);
			float num4 = (float)i / ((float)num * 0.5f);
			float y = num4 - 3f;
			if (i >= num >> 1)
			{
				@int += 1;
				num4 -= 1f;
			}
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_left, v_up, new float2(0f, y), @int.xy, 0f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_left, v_up, new float2(1f, y), @int.xy, 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(0f, y), @int.xy, 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(0.5f, y), @int.yz, 0f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_up, v_right, new float2(1f, y), @int.yz, 1f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_right, v_down, new float2(0f, y), @int.yz, 1f, 0f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_right, v_down, new float2(1f, y), @int.yz, 1f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(0f, y), @int.yz, 1f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(0.5f, y), @int.yz, 0f, -2f, num4);
			AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_down, v_left, new float2(1f, y), @int.xy, 0f, -2f, num4);
			if (i != 0)
			{
				AddQuad(indices, ref indexIndex, vertexIndex - 20, vertexIndex - 10, vertexIndex - 9, vertexIndex - 19);
				AddQuad(indices, ref indexIndex, vertexIndex - 18, vertexIndex - 8, vertexIndex - 7, vertexIndex - 17);
				AddQuad(indices, ref indexIndex, vertexIndex - 17, vertexIndex - 7, vertexIndex - 6, vertexIndex - 16);
				AddQuad(indices, ref indexIndex, vertexIndex - 15, vertexIndex - 5, vertexIndex - 4, vertexIndex - 14);
				AddQuad(indices, ref indexIndex, vertexIndex - 13, vertexIndex - 3, vertexIndex - 2, vertexIndex - 12);
				AddQuad(indices, ref indexIndex, vertexIndex - 12, vertexIndex - 2, vertexIndex - 1, vertexIndex - 11);
			}
		}
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0f, -2f), new int2(5, 3), 1f, -2f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0f, -1f), new int2(5, 3), 1f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0.5f, -1f), new int2(5, 3), 0f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(1f, -1f), new int2(1, 5), 0f, 0f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(1f, -2f), new int2(1, 5), 0f, -2f, 1f);
		AddVertex(vertices, normals, tangents, colors, uvs, ref vertexIndex, v_forward, v_left, new float2(0.5f, -2f), new int2(5, 3), 0f, -2f, 1f);
		AddQuad(indices, ref indexIndex, vertexIndex - 6, vertexIndex - 5, vertexIndex - 4, vertexIndex - 1);
		AddQuad(indices, ref indexIndex, vertexIndex - 1, vertexIndex - 4, vertexIndex - 3, vertexIndex - 2);
		return CreateMesh("Default roundabout", vertices, normals, tangents, colors, uvs, indices);
	}
```

- `private static CreateMesh(System.String name, UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Color32[] colors, UnityEngine.Vector4[] uvs, System.Int32[] indices) : UnityEngine.Mesh`  

```csharp
private static Mesh CreateMesh(string name, Vector3[] vertices, Vector3[] normals, Vector4[] tangents, Color32[] colors, Vector4[] uvs, int[] indices)
	{
		Mesh mesh = new Mesh();
		mesh.name = name;
		mesh.vertices = vertices;
		mesh.normals = normals;
		mesh.tangents = tangents;
		mesh.colors32 = colors;
		mesh.SetUVs(0, uvs);
		mesh.triangles = indices;
		mesh.bounds = new Bounds(Vector3.zero, new Vector3(1000f, 1000f, 1000f));
		return mesh;
	}
```

- `public static UncacheMeshData(Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

```csharp
public static void UncacheMeshData(Entity entity, EntityCommandBuffer commandBuffer)
	{
		commandBuffer.RemoveComponent<MeshVertex>(entity);
		commandBuffer.RemoveComponent<MeshNormal>(entity);
		commandBuffer.RemoveComponent<MeshTangent>(entity);
		commandBuffer.RemoveComponent<MeshUV0>(entity);
		commandBuffer.RemoveComponent<MeshIndex>(entity);
	}
```


## Nested types

- `Game.Rendering.NetMeshHelpers+CacheMeshDataJob`  

