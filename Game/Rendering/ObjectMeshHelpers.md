# Game.Rendering.ObjectMeshHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ObjectMeshHelpers
{
    private static System.Void AddBaseFace(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uv, System.Int32[] indices, System.Int32& vertexIndex, System.Int32& indexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent);
    private static System.Void AddBounds(Game.Rendering.ObjectMeshHelpers+TreeNode& targetNode, System.Int32& sourceSize, Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 sourceIndex);
    private static System.Void AddFace(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uv, System.Int32[] indices, System.Int32& vertexIndex, System.Int32& indexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent);
    private static System.Void AddTriangle(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, Unity.Collections.NativeArray<System.Int32> boneIndex, Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.int3 boneID, System.Int32 triangleIndex);
    private static System.Void AddTriangle(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth, Colossal.Mathematics.Triangle3 triangle, System.Int32 index);
    public static Unity.Jobs.JobHandle CacheMeshData(Game.Prefabs.RenderPrefab meshPrefab, Colossal.IO.AssetDatabase.GeometryAsset meshData, Unity.Entities.Entity entity, System.Int32 boneCount, System.Boolean cacheNormals, Unity.Entities.EntityCommandBuffer commandBuffer);
    public static System.Void CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, System.Boolean cacheNormals, Unity.Entities.EntityCommandBuffer commandBuffer);
    private static System.Void CalculateTreeSize(System.Int32 indexCount, Colossal.Mathematics.Bounds3 bounds, System.Int32& treeDepth, System.Int32& treeSize, Unity.Mathematics.float3& sizeFactor, Unity.Mathematics.float3& sizeOffset);
    public static UnityEngine.Mesh CreateDefaultBaseMesh();
    public static UnityEngine.Mesh CreateDefaultMesh();
    private static System.Void FillBoneData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, System.Int32 vertexOffset, Unity.Collections.NativeSlice<System.Byte> boneIdsData, System.Int32 boneIdsDim, UnityEngine.Rendering.VertexAttributeFormat boneIdsFormat, Unity.Collections.NativeSlice<System.Byte> weightsData, System.Int32 weightsDim, UnityEngine.Rendering.VertexAttributeFormat weightsFormat, Unity.Collections.NativeArray<System.Byte> indexData, UnityEngine.Rendering.IndexFormat indexFormat, System.Int32 indexOffset);
    private static System.Void FillIndices(Game.Rendering.ObjectMeshHelpers+BoneData boneData, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<System.Int32> sourceIndices, Unity.Collections.NativeArray<System.Int32> targetIndices, System.Int32 bone);
    private static System.Void FillIndices(Game.Rendering.ObjectMeshHelpers+BoneData boneData, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<System.UInt16> sourceIndices, Unity.Collections.NativeArray<System.Int32> targetIndices, System.Int32 bone);
    private static System.Void FillMeshData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> sourceNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshNode> targetNodes, Unity.Collections.NativeArray<System.Int32> sourceIndices, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> targetIndices, System.Int32 treeDepth, System.Int32* depthOffsets);
    private static System.Void FillMeshData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> sourceNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshNode> targetNodes, Unity.Collections.NativeArray<System.UInt16> sourceIndices, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> targetIndices, System.Int32 treeDepth, System.Int32* depthOffsets);
    private static System.Void FillTreeNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, Unity.Collections.NativeArray<System.Int32> indices, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth);
    private static System.Void FillTreeNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, Unity.Collections.NativeArray<System.UInt16> indices, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth);
    private static System.Void InitializeBones(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, System.Int32 indexCount);
    private static System.Void InitializeTree(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 treeSize);
    public static System.Void UncacheMeshData(Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer commandBuffer);
    private static System.Void UpdateNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 treeDepth, System.Int32* depthOffsets);
}
```


## Methods

- `private static AddBaseFace(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uv, System.Int32[] indices, System.Int32& vertexIndex, System.Int32& indexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent) : System.Void`  

```csharp
private static void AddBaseFace(Vector3[] vertices, Vector3[] normals, Vector4[] tangents, Vector2[] uv, int[] indices, ref int vertexIndex, ref int indexIndex, float3 normal, float3 tangent)
	{
		float3 @float = math.cross(normal, tangent) * 0.5f;
		float3 float2 = new float3(0f, -1.5f, 0f);
		vertices[vertexIndex] = normal + tangent + @float + float2;
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		uv[vertexIndex] = new Vector2(1f, 0f);
		vertexIndex++;
		vertices[vertexIndex] = normal - tangent + @float + float2;
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		uv[vertexIndex] = new Vector2(0f, 0f);
		vertexIndex++;
		vertices[vertexIndex] = normal - tangent - @float + float2;
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		uv[vertexIndex] = new Vector2(0f, 1f);
		vertexIndex++;
		vertices[vertexIndex] = normal + tangent - @float + float2;
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		uv[vertexIndex] = new Vector2(1f, 1f);
		vertexIndex++;
		indices[indexIndex++] = vertexIndex - 4;
		indices[indexIndex++] = vertexIndex - 3;
		indices[indexIndex++] = vertexIndex - 2;
		indices[indexIndex++] = vertexIndex - 2;
		indices[indexIndex++] = vertexIndex - 1;
		indices[indexIndex++] = vertexIndex - 4;
	}
```

- `private static AddBounds(Game.Rendering.ObjectMeshHelpers+TreeNode& targetNode, System.Int32& sourceSize, Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 sourceIndex) : System.Void`  

```csharp
private static void AddBounds(ref TreeNode targetNode, ref int sourceSize, NativeArray<TreeNode> treeNodes, int sourceIndex)
	{
		TreeNode value = treeNodes[sourceIndex];
		if (value.m_ItemCount != 0)
		{
			targetNode.m_Bounds |= value.m_Bounds;
			targetNode.m_ItemCount++;
			if (value.m_ItemCount != 1)
			{
				value.m_NodeIndex = sourceSize++;
				treeNodes[sourceIndex] = value;
			}
		}
	}
```

- `private static AddFace(UnityEngine.Vector3[] vertices, UnityEngine.Vector3[] normals, UnityEngine.Vector4[] tangents, UnityEngine.Vector2[] uv, System.Int32[] indices, System.Int32& vertexIndex, System.Int32& indexIndex, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 tangent) : System.Void`  

```csharp
private static void AddFace(Vector3[] vertices, Vector3[] normals, Vector4[] tangents, Vector2[] uv, int[] indices, ref int vertexIndex, ref int indexIndex, float3 normal, float3 tangent)
	{
		float3 @float = math.cross(normal, tangent);
		vertices[vertexIndex] = normal + tangent + @float;
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		uv[vertexIndex] = new Vector2(1f, 0f);
		vertexIndex++;
		vertices[vertexIndex] = normal - tangent + @float;
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		uv[vertexIndex] = new Vector2(0f, 0f);
		vertexIndex++;
		vertices[vertexIndex] = normal - tangent - @float;
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		uv[vertexIndex] = new Vector2(0f, 1f);
		vertexIndex++;
		vertices[vertexIndex] = normal + tangent - @float;
		normals[vertexIndex] = normal;
		tangents[vertexIndex] = new float4(tangent, -1f);
		uv[vertexIndex] = new Vector2(1f, 1f);
		vertexIndex++;
		indices[indexIndex++] = vertexIndex - 4;
		indices[indexIndex++] = vertexIndex - 3;
		indices[indexIndex++] = vertexIndex - 2;
		indices[indexIndex++] = vertexIndex - 2;
		indices[indexIndex++] = vertexIndex - 1;
		indices[indexIndex++] = vertexIndex - 4;
	}
```

- `private static AddTriangle(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, Unity.Collections.NativeArray<System.Int32> boneIndex, Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.int3 boneID, System.Int32 triangleIndex) : System.Void`  

```csharp
private static void AddTriangle(NativeArray<TreeNode> treeNodes, NativeArray<int> nextTriangle, float3 sizeOffset, float3 sizeFactor, int treeDepth, Triangle3 triangle, int index)
	{
		Bounds3 bounds = MathUtils.Bounds(triangle);
		float3 @float = MathUtils.Center(bounds) * sizeFactor + sizeOffset;
		float num = math.cmax(MathUtils.Size(bounds) * sizeFactor);
		int num2 = treeDepth - 1;
		int num3 = 0;
		int num4 = 0;
		while (num <= 0.5f && num4 < num2)
		{
			num3 += 1 << 3 * num4++;
			num *= 2f;
		}
		int num5 = 1 << num4;
		int3 x = math.clamp((int3)(@float * num5), 0, num5 - 1);
		num3 += math.dot(x, new int3(1, num5, num5 * num5));
		TreeNode value = treeNodes[num3];
		nextTriangle[index] = value.m_FirstTriangle;
		value.m_Bounds |= bounds;
		value.m_FirstTriangle = index;
		value.m_ItemCount++;
		treeNodes[num3] = value;
	}
```

- `private static AddTriangle(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth, Colossal.Mathematics.Triangle3 triangle, System.Int32 index) : System.Void`  

```csharp
private static void AddTriangle(NativeArray<TreeNode> treeNodes, NativeArray<int> nextTriangle, float3 sizeOffset, float3 sizeFactor, int treeDepth, Triangle3 triangle, int index)
	{
		Bounds3 bounds = MathUtils.Bounds(triangle);
		float3 @float = MathUtils.Center(bounds) * sizeFactor + sizeOffset;
		float num = math.cmax(MathUtils.Size(bounds) * sizeFactor);
		int num2 = treeDepth - 1;
		int num3 = 0;
		int num4 = 0;
		while (num <= 0.5f && num4 < num2)
		{
			num3 += 1 << 3 * num4++;
			num *= 2f;
		}
		int num5 = 1 << num4;
		int3 x = math.clamp((int3)(@float * num5), 0, num5 - 1);
		num3 += math.dot(x, new int3(1, num5, num5 * num5));
		TreeNode value = treeNodes[num3];
		nextTriangle[index] = value.m_FirstTriangle;
		value.m_Bounds |= bounds;
		value.m_FirstTriangle = index;
		value.m_ItemCount++;
		treeNodes[num3] = value;
	}
```

- `public static CacheMeshData(Game.Prefabs.RenderPrefab meshPrefab, Colossal.IO.AssetDatabase.GeometryAsset meshData, Unity.Entities.Entity entity, System.Int32 boneCount, System.Boolean cacheNormals, Unity.Entities.EntityCommandBuffer commandBuffer) : Unity.Jobs.JobHandle`  

```csharp
public static void CacheMeshData(Mesh mesh, Entity entity, bool cacheNormals, EntityCommandBuffer commandBuffer)
	{
		DynamicBuffer<MeshVertex> dynamicBuffer = commandBuffer.AddBuffer<MeshVertex>(entity);
		DynamicBuffer<MeshIndex> dynamicBuffer2 = commandBuffer.AddBuffer<MeshIndex>(entity);
		DynamicBuffer<MeshNormal> dynamicBuffer3 = default(DynamicBuffer<MeshNormal>);
		if (cacheNormals)
		{
			dynamicBuffer3 = commandBuffer.AddBuffer<MeshNormal>(entity);
		}
		Mesh.MeshDataArray meshDataArray = Mesh.AcquireReadOnlyMeshData(mesh);
		Mesh.MeshData meshData = meshDataArray[0];
		int num = 0;
		int subMeshCount = meshData.subMeshCount;
		for (int i = 0; i < subMeshCount; i++)
		{
			num += meshData.GetSubMesh(i).indexCount;
		}
		dynamicBuffer.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer2.ResizeUninitialized(num);
		meshData.GetVertices(dynamicBuffer.AsNativeArray().Reinterpret<Vector3>());
		if (cacheNormals)
		{
			dynamicBuffer3.ResizeUninitialized(meshData.vertexCount);
			meshData.GetNormals(dynamicBuffer3.AsNativeArray().Reinterpret<Vector3>());
		}
		num = 0;
		for (int j = 0; j < subMeshCount; j++)
		{
			int indexCount = meshData.GetSubMesh(j).indexCount;
			meshData.GetIndices(dynamicBuffer2.AsNativeArray().GetSubArray(num, indexCount).Reinterpret<int>(), j);
			num += indexCount;
		}
		meshDataArray.Dispose();
	}
```

- `public static CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, System.Boolean cacheNormals, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

```csharp
public static void CacheMeshData(Mesh mesh, Entity entity, bool cacheNormals, EntityCommandBuffer commandBuffer)
	{
		DynamicBuffer<MeshVertex> dynamicBuffer = commandBuffer.AddBuffer<MeshVertex>(entity);
		DynamicBuffer<MeshIndex> dynamicBuffer2 = commandBuffer.AddBuffer<MeshIndex>(entity);
		DynamicBuffer<MeshNormal> dynamicBuffer3 = default(DynamicBuffer<MeshNormal>);
		if (cacheNormals)
		{
			dynamicBuffer3 = commandBuffer.AddBuffer<MeshNormal>(entity);
		}
		Mesh.MeshDataArray meshDataArray = Mesh.AcquireReadOnlyMeshData(mesh);
		Mesh.MeshData meshData = meshDataArray[0];
		int num = 0;
		int subMeshCount = meshData.subMeshCount;
		for (int i = 0; i < subMeshCount; i++)
		{
			num += meshData.GetSubMesh(i).indexCount;
		}
		dynamicBuffer.ResizeUninitialized(meshData.vertexCount);
		dynamicBuffer2.ResizeUninitialized(num);
		meshData.GetVertices(dynamicBuffer.AsNativeArray().Reinterpret<Vector3>());
		if (cacheNormals)
		{
			dynamicBuffer3.ResizeUninitialized(meshData.vertexCount);
			meshData.GetNormals(dynamicBuffer3.AsNativeArray().Reinterpret<Vector3>());
		}
		num = 0;
		for (int j = 0; j < subMeshCount; j++)
		{
			int indexCount = meshData.GetSubMesh(j).indexCount;
			meshData.GetIndices(dynamicBuffer2.AsNativeArray().GetSubArray(num, indexCount).Reinterpret<int>(), j);
			num += indexCount;
		}
		meshDataArray.Dispose();
	}
```

- `private static CalculateTreeSize(System.Int32 indexCount, Colossal.Mathematics.Bounds3 bounds, System.Int32& treeDepth, System.Int32& treeSize, Unity.Mathematics.float3& sizeFactor, Unity.Mathematics.float3& sizeOffset) : System.Void`  

```csharp
private static void CalculateTreeSize(int indexCount, Bounds3 bounds, out int treeDepth, out int treeSize, out float3 sizeFactor, out float3 sizeOffset)
	{
		treeDepth = 1;
		treeSize = 1;
		for (int num = indexCount / 3; num >= 32; num >>= 3)
		{
			treeSize += 1 << 3 * treeDepth++;
		}
		sizeFactor = 1f / math.max(0.001f, MathUtils.Size(bounds));
		sizeOffset = 0.5f - MathUtils.Center(bounds) * sizeFactor;
	}
```

- `public static CreateDefaultBaseMesh() : UnityEngine.Mesh`  

```csharp
public static Mesh CreateDefaultBaseMesh()
	{
		int num = 24;
		Vector3[] vertices = new Vector3[16];
		Vector3[] normals = new Vector3[16];
		Vector4[] tangents = new Vector4[16];
		Vector2[] uv = new Vector2[16];
		int[] array = new int[num];
		int vertexIndex = 0;
		int indexIndex = 0;
		AddBaseFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(-1f, 0f, 0f), new float3(0f, 0f, -1f));
		AddBaseFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(0f, 0f, -1f), new float3(1f, 0f, 0f));
		AddBaseFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(1f, 0f, 0f), new float3(0f, 0f, 1f));
		AddBaseFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(0f, 0f, 1f), new float3(-1f, 0f, 0f));
		return new Mesh
		{
			name = "Default base",
			vertices = vertices,
			normals = normals,
			tangents = tangents,
			uv = uv,
			triangles = array
		};
	}
```

- `public static CreateDefaultMesh() : UnityEngine.Mesh`  

```csharp
public static Mesh CreateDefaultMesh()
	{
		int num = 36;
		Vector3[] vertices = new Vector3[24];
		Vector3[] normals = new Vector3[24];
		Vector4[] tangents = new Vector4[24];
		Vector2[] uv = new Vector2[24];
		int[] array = new int[num];
		int vertexIndex = 0;
		int indexIndex = 0;
		AddFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(-1f, 0f, 0f), new float3(0f, 1f, 0f));
		AddFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(0f, -1f, 0f), new float3(0f, 0f, 1f));
		AddFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(0f, 0f, -1f), new float3(1f, 0f, 0f));
		AddFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(1f, 0f, 0f), new float3(0f, -1f, 0f));
		AddFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(0f, 1f, 0f), new float3(0f, 0f, -1f));
		AddFace(vertices, normals, tangents, uv, array, ref vertexIndex, ref indexIndex, new float3(0f, 0f, 1f), new float3(-1f, 0f, 0f));
		return new Mesh
		{
			name = "Default object",
			vertices = vertices,
			normals = normals,
			tangents = tangents,
			uv = uv,
			triangles = array
		};
	}
```

- `private static FillBoneData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, System.Int32 vertexOffset, Unity.Collections.NativeSlice<System.Byte> boneIdsData, System.Int32 boneIdsDim, UnityEngine.Rendering.VertexAttributeFormat boneIdsFormat, Unity.Collections.NativeSlice<System.Byte> weightsData, System.Int32 weightsDim, UnityEngine.Rendering.VertexAttributeFormat weightsFormat, Unity.Collections.NativeArray<System.Byte> indexData, UnityEngine.Rendering.IndexFormat indexFormat, System.Int32 indexOffset) : System.Void`  

```csharp
private unsafe static void FillBoneData(NativeArray<BoneData> bones, NativeArray<int> boneIndex, NativeArray<MeshVertex> vertices, int vertexOffset, NativeSlice<byte> boneIdsData, int boneIdsDim, VertexAttributeFormat boneIdsFormat, NativeSlice<byte> weightsData, int weightsDim, VertexAttributeFormat weightsFormat, NativeArray<byte> indexData, IndexFormat indexFormat, int indexOffset)
	{
		int* ptr = (int*)indexData.GetUnsafeReadOnlyPtr();
		ushort* ptr2 = (ushort*)indexData.GetUnsafeReadOnlyPtr();
		bool flag = boneIdsFormat == VertexAttributeFormat.UInt8;
		byte* unsafeReadOnlyPtr = (byte*)boneIdsData.GetUnsafeReadOnlyPtr();
		bool flag2 = weightsFormat == VertexAttributeFormat.UNorm8;
		byte* unsafeReadOnlyPtr2 = (byte*)weightsData.GetUnsafeReadOnlyPtr();
		int num = ((indexFormat == IndexFormat.UInt16) ? 2 : 4);
		int num2 = indexData.Length / (3 * num);
		indexOffset /= 3;
		int3 @int = default(int3);
		for (int i = 0; i < num2; i++)
		{
			if (num == 2)
			{
				@int.x = *ptr2;
				@int.y = ptr2[1];
				@int.z = ptr2[2];
			}
			else
			{
				@int.x = *ptr;
				@int.y = ptr[1];
				@int.z = ptr[2];
			}
			@int -= vertexOffset;
			Triangle3 triangle = new Triangle3(vertices[@int.x].m_Vertex, vertices[@int.y].m_Vertex, vertices[@int.z].m_Vertex);
			int3 int2 = @int * boneIdsDim;
			int3 falseValue = ((!flag) ? new int3(((int*)unsafeReadOnlyPtr)[int2.x], ((int*)unsafeReadOnlyPtr)[int2.y], ((int*)unsafeReadOnlyPtr)[int2.z]) : new int3(unsafeReadOnlyPtr[int2.x], unsafeReadOnlyPtr[int2.y], unsafeReadOnlyPtr[int2.z]));
			int3 int3 = @int * weightsDim;
			falseValue = math.select(test: (weightsDim != 0) ? ((!flag2) ? (new float3(((float*)unsafeReadOnlyPtr2)[int3.x], ((float*)unsafeReadOnlyPtr2)[int3.y], ((float*)unsafeReadOnlyPtr2)[int3.z]) < new float3(0.5f)) : (new float3((int)unsafeReadOnlyPtr2[int3.x], (int)unsafeReadOnlyPtr2[int3.y], (int)unsafeReadOnlyPtr2[int3.z]) < new float3(128))) : ((bool3)false), falseValue: falseValue, trueValue: new int3(-1));
			AddTriangle(bones, boneIndex, triangle, falseValue, indexOffset + i);
			ptr += 3;
			ptr2 += 3;
		}
	}
```

- `private static FillIndices(Game.Rendering.ObjectMeshHelpers+BoneData boneData, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<System.Int32> sourceIndices, Unity.Collections.NativeArray<System.Int32> targetIndices, System.Int32 bone) : System.Void`  

```csharp
private static void FillIndices(BoneData boneData, NativeArray<int> boneIndex, NativeArray<ushort> sourceIndices, NativeArray<int> targetIndices, int bone)
	{
		int num = 0;
		for (int i = boneData.m_TriangleRange.x; i <= boneData.m_TriangleRange.y; i++)
		{
			if (boneIndex[i] == bone)
			{
				int3 @int = i * 3 + new int3(0, 1, 2);
				targetIndices[num++] = sourceIndices[@int.x];
				targetIndices[num++] = sourceIndices[@int.y];
				targetIndices[num++] = sourceIndices[@int.z];
			}
		}
	}
```

- `private static FillIndices(Game.Rendering.ObjectMeshHelpers+BoneData boneData, Unity.Collections.NativeArray<System.Int32> boneIndex, Unity.Collections.NativeArray<System.UInt16> sourceIndices, Unity.Collections.NativeArray<System.Int32> targetIndices, System.Int32 bone) : System.Void`  

```csharp
private static void FillIndices(BoneData boneData, NativeArray<int> boneIndex, NativeArray<ushort> sourceIndices, NativeArray<int> targetIndices, int bone)
	{
		int num = 0;
		for (int i = boneData.m_TriangleRange.x; i <= boneData.m_TriangleRange.y; i++)
		{
			if (boneIndex[i] == bone)
			{
				int3 @int = i * 3 + new int3(0, 1, 2);
				targetIndices[num++] = sourceIndices[@int.x];
				targetIndices[num++] = sourceIndices[@int.y];
				targetIndices[num++] = sourceIndices[@int.z];
			}
		}
	}
```

- `private static FillMeshData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> sourceNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshNode> targetNodes, Unity.Collections.NativeArray<System.Int32> sourceIndices, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> targetIndices, System.Int32 treeDepth, System.Int32* depthOffsets) : System.Void`  

```csharp
private unsafe static void FillMeshData(NativeArray<TreeNode> sourceNodes, NativeArray<int> nextTriangle, NativeArray<MeshNode> targetNodes, NativeArray<ushort> sourceIndices, NativeArray<MeshIndex> targetIndices, int treeDepth, int* depthOffsets)
	{
		int* ptr = stackalloc int[128];
		int* ptr2 = stackalloc int[128];
		int* ptr3 = stackalloc int[128];
		int num = 1;
		int num2 = 0;
		*ptr = 0;
		*ptr2 = 0;
		*ptr3 = 0;
		while (--num >= 0)
		{
			int num3 = ptr[num];
			int num4 = ptr2[num];
			int num5 = ptr3[num];
			int num6 = 1 << num5;
			TreeNode treeNode = sourceNodes[num3 + num4];
			int x = num2;
			int num7 = treeNode.m_FirstTriangle;
			while (num7 >= 0)
			{
				int3 @int = num7 * 3 + new int3(0, 1, 2);
				int3 int2 = num2 + new int3(0, 1, 2);
				targetIndices[int2.x] = new MeshIndex(sourceIndices[@int.x]);
				targetIndices[int2.y] = new MeshIndex(sourceIndices[@int.y]);
				targetIndices[int2.z] = new MeshIndex(sourceIndices[@int.z]);
				num7 = nextTriangle[num7];
				num2 += 3;
			}
			int num8 = 0;
			int4 subNodes = -1;
			int4 subNodes2 = -1;
			if (num5 + 1 < treeDepth)
			{
				int3 int3 = new int3(num4, num4 >> num5, num4 >> num5 + num5) & (num6 - 1);
				for (int i = 0; i < 8; i++)
				{
					int num9 = num3 + (1 << 3 * num5);
					int num10 = num5 + 1;
					int3 x2 = int3 * 2 + math.select((int3)0, (int3)1, (i & new int3(1, 2, 4)) != 0);
					while (num10 < treeDepth)
					{
						int num11 = 1 << num10;
						int num12 = math.dot(x2, new int3(1, num11, num11 * num11));
						TreeNode treeNode2 = sourceNodes[num9 + num12];
						if (treeNode2.m_ItemCount == 1)
						{
							if (treeNode2.m_FirstTriangle != -1)
							{
								int3 int4 = treeNode2.m_FirstTriangle * 3 + new int3(0, 1, 2);
								int3 int5 = num2 + new int3(0, 1, 2);
								targetIndices[int5.x] = new MeshIndex(sourceIndices[int4.x]);
								targetIndices[int5.y] = new MeshIndex(sourceIndices[int4.y]);
								targetIndices[int5.z] = new MeshIndex(sourceIndices[int4.z]);
								num2 += 3;
								break;
							}
							num9 += 1 << 3 * num10++;
							x2 *= 2;
							continue;
						}
						if (treeNode2.m_ItemCount != 0)
						{
							if (num8 < 4)
							{
								subNodes[num8++] = depthOffsets[num10] + treeNode2.m_NodeIndex;
							}
							else
							{
								subNodes2[num8++ - 4] = depthOffsets[num10] + treeNode2.m_NodeIndex;
							}
							ptr[num] = num9;
							ptr2[num] = num12;
							ptr3[num] = num10;
							num++;
							break;
						}
						if (num10 == num5 + 1)
						{
							break;
						}
						if ((x2.x & 1) == 0)
						{
							x2.x++;
							continue;
						}
						if ((x2.y & 1) == 0)
						{
							x2.xy += new int2(-1, 1);
							continue;
						}
						if ((x2.z & 1) != 0)
						{
							break;
						}
						x2 += new int3(-1, -1, 1);
					}
				}
			}
			int index = depthOffsets[num5] + treeNode.m_NodeIndex;
			targetNodes[index] = new MeshNode
			{
				m_Bounds = treeNode.m_Bounds,
				m_IndexRange = new int2(x, num2),
				m_SubNodes1 = subNodes,
				m_SubNodes2 = subNodes2
			};
		}
	}
```

- `private static FillMeshData(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> sourceNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshNode> targetNodes, Unity.Collections.NativeArray<System.UInt16> sourceIndices, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> targetIndices, System.Int32 treeDepth, System.Int32* depthOffsets) : System.Void`  

```csharp
private unsafe static void FillMeshData(NativeArray<TreeNode> sourceNodes, NativeArray<int> nextTriangle, NativeArray<MeshNode> targetNodes, NativeArray<ushort> sourceIndices, NativeArray<MeshIndex> targetIndices, int treeDepth, int* depthOffsets)
	{
		int* ptr = stackalloc int[128];
		int* ptr2 = stackalloc int[128];
		int* ptr3 = stackalloc int[128];
		int num = 1;
		int num2 = 0;
		*ptr = 0;
		*ptr2 = 0;
		*ptr3 = 0;
		while (--num >= 0)
		{
			int num3 = ptr[num];
			int num4 = ptr2[num];
			int num5 = ptr3[num];
			int num6 = 1 << num5;
			TreeNode treeNode = sourceNodes[num3 + num4];
			int x = num2;
			int num7 = treeNode.m_FirstTriangle;
			while (num7 >= 0)
			{
				int3 @int = num7 * 3 + new int3(0, 1, 2);
				int3 int2 = num2 + new int3(0, 1, 2);
				targetIndices[int2.x] = new MeshIndex(sourceIndices[@int.x]);
				targetIndices[int2.y] = new MeshIndex(sourceIndices[@int.y]);
				targetIndices[int2.z] = new MeshIndex(sourceIndices[@int.z]);
				num7 = nextTriangle[num7];
				num2 += 3;
			}
			int num8 = 0;
			int4 subNodes = -1;
			int4 subNodes2 = -1;
			if (num5 + 1 < treeDepth)
			{
				int3 int3 = new int3(num4, num4 >> num5, num4 >> num5 + num5) & (num6 - 1);
				for (int i = 0; i < 8; i++)
				{
					int num9 = num3 + (1 << 3 * num5);
					int num10 = num5 + 1;
					int3 x2 = int3 * 2 + math.select((int3)0, (int3)1, (i & new int3(1, 2, 4)) != 0);
					while (num10 < treeDepth)
					{
						int num11 = 1 << num10;
						int num12 = math.dot(x2, new int3(1, num11, num11 * num11));
						TreeNode treeNode2 = sourceNodes[num9 + num12];
						if (treeNode2.m_ItemCount == 1)
						{
							if (treeNode2.m_FirstTriangle != -1)
							{
								int3 int4 = treeNode2.m_FirstTriangle * 3 + new int3(0, 1, 2);
								int3 int5 = num2 + new int3(0, 1, 2);
								targetIndices[int5.x] = new MeshIndex(sourceIndices[int4.x]);
								targetIndices[int5.y] = new MeshIndex(sourceIndices[int4.y]);
								targetIndices[int5.z] = new MeshIndex(sourceIndices[int4.z]);
								num2 += 3;
								break;
							}
							num9 += 1 << 3 * num10++;
							x2 *= 2;
							continue;
						}
						if (treeNode2.m_ItemCount != 0)
						{
							if (num8 < 4)
							{
								subNodes[num8++] = depthOffsets[num10] + treeNode2.m_NodeIndex;
							}
							else
							{
								subNodes2[num8++ - 4] = depthOffsets[num10] + treeNode2.m_NodeIndex;
							}
							ptr[num] = num9;
							ptr2[num] = num12;
							ptr3[num] = num10;
							num++;
							break;
						}
						if (num10 == num5 + 1)
						{
							break;
						}
						if ((x2.x & 1) == 0)
						{
							x2.x++;
							continue;
						}
						if ((x2.y & 1) == 0)
						{
							x2.xy += new int2(-1, 1);
							continue;
						}
						if ((x2.z & 1) != 0)
						{
							break;
						}
						x2 += new int3(-1, -1, 1);
					}
				}
			}
			int index = depthOffsets[num5] + treeNode.m_NodeIndex;
			targetNodes[index] = new MeshNode
			{
				m_Bounds = treeNode.m_Bounds,
				m_IndexRange = new int2(x, num2),
				m_SubNodes1 = subNodes,
				m_SubNodes2 = subNodes2
			};
		}
	}
```

- `private static FillTreeNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, Unity.Collections.NativeArray<System.Int32> indices, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth) : System.Void`  

```csharp
private static void FillTreeNodes(NativeArray<TreeNode> treeNodes, NativeArray<int> nextTriangle, NativeArray<MeshVertex> vertices, NativeArray<ushort> indices, float3 sizeOffset, float3 sizeFactor, int treeDepth)
	{
		int length = nextTriangle.Length;
		for (int i = 0; i < length; i++)
		{
			int3 @int = i * 3 + new int3(0, 1, 2);
			AddTriangle(triangle: new Triangle3(vertices[indices[@int.x]].m_Vertex, vertices[indices[@int.y]].m_Vertex, vertices[indices[@int.z]].m_Vertex), treeNodes: treeNodes, nextTriangle: nextTriangle, sizeOffset: sizeOffset, sizeFactor: sizeFactor, treeDepth: treeDepth, index: i);
		}
	}
```

- `private static FillTreeNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, Unity.Collections.NativeArray<System.Int32> nextTriangle, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> vertices, Unity.Collections.NativeArray<System.UInt16> indices, Unity.Mathematics.float3 sizeOffset, Unity.Mathematics.float3 sizeFactor, System.Int32 treeDepth) : System.Void`  

```csharp
private static void FillTreeNodes(NativeArray<TreeNode> treeNodes, NativeArray<int> nextTriangle, NativeArray<MeshVertex> vertices, NativeArray<ushort> indices, float3 sizeOffset, float3 sizeFactor, int treeDepth)
	{
		int length = nextTriangle.Length;
		for (int i = 0; i < length; i++)
		{
			int3 @int = i * 3 + new int3(0, 1, 2);
			AddTriangle(triangle: new Triangle3(vertices[indices[@int.x]].m_Vertex, vertices[indices[@int.y]].m_Vertex, vertices[indices[@int.z]].m_Vertex), treeNodes: treeNodes, nextTriangle: nextTriangle, sizeOffset: sizeOffset, sizeFactor: sizeFactor, treeDepth: treeDepth, index: i);
		}
	}
```

- `private static InitializeBones(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+BoneData> bones, System.Int32 indexCount) : System.Void`  

```csharp
private static void InitializeBones(NativeArray<BoneData> bones, int indexCount)
	{
		int length = bones.Length;
		int x = indexCount / 3;
		for (int i = 0; i < length; i++)
		{
			bones[i] = new BoneData
			{
				m_Bounds = new Bounds3(float.MaxValue, float.MinValue),
				m_TriangleRange = new int2(x, -1)
			};
		}
	}
```

- `private static InitializeTree(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 treeSize) : System.Void`  

```csharp
private static void InitializeTree(NativeArray<TreeNode> treeNodes, int treeSize)
	{
		for (int i = 0; i < treeSize; i++)
		{
			treeNodes[i] = new TreeNode
			{
				m_Bounds = new Bounds3(float.MaxValue, float.MinValue),
				m_FirstTriangle = -1
			};
		}
	}
```

- `public static UncacheMeshData(Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

```csharp
public static void UncacheMeshData(Entity entity, EntityCommandBuffer commandBuffer)
	{
		commandBuffer.RemoveComponent<MeshVertex>(entity);
		commandBuffer.RemoveComponent<MeshNormal>(entity);
		commandBuffer.RemoveComponent<MeshIndex>(entity);
		commandBuffer.RemoveComponent<MeshNode>(entity);
	}
```

- `private static UpdateNodes(Unity.Collections.NativeArray<Game.Rendering.ObjectMeshHelpers+TreeNode> treeNodes, System.Int32 treeDepth, System.Int32* depthOffsets) : System.Void`  

```csharp
private unsafe static void UpdateNodes(NativeArray<TreeNode> treeNodes, int treeDepth, int* depthOffsets)
	{
		int num = treeDepth - 1;
		int num2 = 0;
		int num3 = 0;
		while (num3 < num)
		{
			num2 += 1 << 3 * num3++;
		}
		int3 x = default(int3);
		while (num3 > 0)
		{
			int num4 = 1 << num3;
			int num5 = num2;
			num2 -= 1 << 3 * --num3;
			int num6 = 1 << num3;
			int num7 = num2;
			int3 y = new int3(2, num4 << 1, num4 * num4 << 1);
			int3 y2 = new int3(1, num6, num6 * num6);
			int4 @int = new int4(0, 1, num4, num4 + 1);
			int4 int2 = num4 * num4 + @int;
			int sourceSize = 0;
			x.z = 0;
			while (x.z < num6)
			{
				x.y = 0;
				while (x.y < num6)
				{
					x.x = 0;
					while (x.x < num6)
					{
						int num8 = num5 + math.dot(x, y);
						int index = num7 + math.dot(x, y2);
						int4 int3 = num8 + @int;
						int4 int4 = num8 + int2;
						TreeNode targetNode = treeNodes[index];
						AddBounds(ref targetNode, ref sourceSize, treeNodes, int3.x);
						AddBounds(ref targetNode, ref sourceSize, treeNodes, int3.y);
						AddBounds(ref targetNode, ref sourceSize, treeNodes, int3.z);
						AddBounds(ref targetNode, ref sourceSize, treeNodes, int3.w);
						AddBounds(ref targetNode, ref sourceSize, treeNodes, int4.x);
						AddBounds(ref targetNode, ref sourceSize, treeNodes, int4.y);
						AddBounds(ref targetNode, ref sourceSize, treeNodes, int4.z);
						AddBounds(ref targetNode, ref sourceSize, treeNodes, int4.w);
						treeNodes[index] = targetNode;
						x.x++;
					}
					x.y++;
				}
				x.z++;
			}
			depthOffsets[num3 + 2] = sourceSize;
		}
		*depthOffsets = 0;
		depthOffsets[1] = 1;
		for (int i = 1; i <= treeDepth; i++)
		{
			depthOffsets[i] += depthOffsets[i - 1];
		}
	}
```


## Nested types

- `Game.Rendering.ObjectMeshHelpers+TreeNode`  
- `Game.Rendering.ObjectMeshHelpers+CacheMeshDataJob`  
- `Game.Rendering.ObjectMeshHelpers+CacheProceduralMeshDataJob`  
- `Game.Rendering.ObjectMeshHelpers+BoneData`  

