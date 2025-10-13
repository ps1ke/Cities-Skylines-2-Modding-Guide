# Game.Objects.RaycastJobs

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class RaycastJobs
{
    private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
    private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
    private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
    private static System.Boolean CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit);
}
```


## Methods

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
private unsafe static bool CheckMeshIntersect(Line3.Segment localLine, DynamicBuffer<MeshVertex> vertices, DynamicBuffer<MeshIndex> indices, DynamicBuffer<MeshNode> nodes, DynamicBuffer<ProceduralBone> prefabBones, DynamicBuffer<Bone> bones, Skeleton skeleton, int2 elementIndex, ref RaycastHit hit)
	{
		bool result = false;
		int* ptr = stackalloc int[128];
		for (int i = 0; i < prefabBones.Length; i++)
		{
			int num = 0;
			Line3.Segment line = default(Line3.Segment);
			ProceduralBone proceduralBone = prefabBones[i];
			if (math.any(MathUtils.Size(nodes[proceduralBone.m_BindIndex].m_Bounds) > 0f))
			{
				ptr[num++] = proceduralBone.m_BindIndex;
				Bone bone = bones[skeleton.m_BoneOffset + i];
				float4x4 float4x = float4x4.TRS(bone.m_Position, bone.m_Rotation, bone.m_Scale);
				int parentIndex = proceduralBone.m_ParentIndex;
				while (parentIndex >= 0)
				{
					Bone bone2 = bones[skeleton.m_BoneOffset + parentIndex];
					ProceduralBone proceduralBone2 = prefabBones[parentIndex];
					float4x = math.mul(float4x4.TRS(bone2.m_Position, bone2.m_Rotation, bone2.m_Scale), float4x);
					parentIndex = proceduralBone2.m_ParentIndex;
				}
				float4x = math.mul(float4x, proceduralBone.m_BindPose);
				float4x = math.inverse(float4x);
				line.a = math.mul(float4x, new float4(localLine.a, 1f)).xyz;
				line.b = math.mul(float4x, new float4(localLine.b, 1f)).xyz;
			}
			while (--num >= 0)
			{
				int index = ptr[num];
				MeshNode meshNode = nodes[index];
				if (!MathUtils.Intersect(meshNode.m_Bounds, line, out var _))
				{
					continue;
				}
				for (int j = meshNode.m_IndexRange.x; j < meshNode.m_IndexRange.y; j += 3)
				{
					Triangle3 triangle = new Triangle3(vertices[indices[j].m_Index].m_Vertex, vertices[indices[j + 1].m_Index].m_Vertex, vertices[indices[j + 2].m_Index].m_Vertex);
					if (MathUtils.Intersect(triangle, line, out var t2) && t2.z < hit.m_NormalizedDistance)
					{
						hit.m_HitDirection = MathUtils.NormalCW(triangle);
						hit.m_NormalizedDistance = t2.z;
						hit.m_CellIndex = elementIndex;
						result = true;
					}
				}
				ptr[num] = meshNode.m_SubNodes1.x;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.x != -1);
				ptr[num] = meshNode.m_SubNodes1.y;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.y != -1);
				ptr[num] = meshNode.m_SubNodes1.z;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.z != -1);
				ptr[num] = meshNode.m_SubNodes1.w;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.w != -1);
				ptr[num] = meshNode.m_SubNodes2.x;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.x != -1);
				ptr[num] = meshNode.m_SubNodes2.y;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.y != -1);
				ptr[num] = meshNode.m_SubNodes2.z;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.z != -1);
				ptr[num] = meshNode.m_SubNodes2.w;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.w != -1);
			}
		}
		return result;
	}
```

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
private unsafe static bool CheckMeshIntersect(Line3.Segment localLine, DynamicBuffer<MeshVertex> vertices, DynamicBuffer<MeshIndex> indices, DynamicBuffer<MeshNode> nodes, DynamicBuffer<ProceduralBone> prefabBones, DynamicBuffer<Bone> bones, Skeleton skeleton, int2 elementIndex, ref RaycastHit hit)
	{
		bool result = false;
		int* ptr = stackalloc int[128];
		for (int i = 0; i < prefabBones.Length; i++)
		{
			int num = 0;
			Line3.Segment line = default(Line3.Segment);
			ProceduralBone proceduralBone = prefabBones[i];
			if (math.any(MathUtils.Size(nodes[proceduralBone.m_BindIndex].m_Bounds) > 0f))
			{
				ptr[num++] = proceduralBone.m_BindIndex;
				Bone bone = bones[skeleton.m_BoneOffset + i];
				float4x4 float4x = float4x4.TRS(bone.m_Position, bone.m_Rotation, bone.m_Scale);
				int parentIndex = proceduralBone.m_ParentIndex;
				while (parentIndex >= 0)
				{
					Bone bone2 = bones[skeleton.m_BoneOffset + parentIndex];
					ProceduralBone proceduralBone2 = prefabBones[parentIndex];
					float4x = math.mul(float4x4.TRS(bone2.m_Position, bone2.m_Rotation, bone2.m_Scale), float4x);
					parentIndex = proceduralBone2.m_ParentIndex;
				}
				float4x = math.mul(float4x, proceduralBone.m_BindPose);
				float4x = math.inverse(float4x);
				line.a = math.mul(float4x, new float4(localLine.a, 1f)).xyz;
				line.b = math.mul(float4x, new float4(localLine.b, 1f)).xyz;
			}
			while (--num >= 0)
			{
				int index = ptr[num];
				MeshNode meshNode = nodes[index];
				if (!MathUtils.Intersect(meshNode.m_Bounds, line, out var _))
				{
					continue;
				}
				for (int j = meshNode.m_IndexRange.x; j < meshNode.m_IndexRange.y; j += 3)
				{
					Triangle3 triangle = new Triangle3(vertices[indices[j].m_Index].m_Vertex, vertices[indices[j + 1].m_Index].m_Vertex, vertices[indices[j + 2].m_Index].m_Vertex);
					if (MathUtils.Intersect(triangle, line, out var t2) && t2.z < hit.m_NormalizedDistance)
					{
						hit.m_HitDirection = MathUtils.NormalCW(triangle);
						hit.m_NormalizedDistance = t2.z;
						hit.m_CellIndex = elementIndex;
						result = true;
					}
				}
				ptr[num] = meshNode.m_SubNodes1.x;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.x != -1);
				ptr[num] = meshNode.m_SubNodes1.y;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.y != -1);
				ptr[num] = meshNode.m_SubNodes1.z;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.z != -1);
				ptr[num] = meshNode.m_SubNodes1.w;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.w != -1);
				ptr[num] = meshNode.m_SubNodes2.x;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.x != -1);
				ptr[num] = meshNode.m_SubNodes2.y;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.y != -1);
				ptr[num] = meshNode.m_SubNodes2.z;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.z != -1);
				ptr[num] = meshNode.m_SubNodes2.w;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.w != -1);
			}
		}
		return result;
	}
```

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
private unsafe static bool CheckMeshIntersect(Line3.Segment localLine, DynamicBuffer<MeshVertex> vertices, DynamicBuffer<MeshIndex> indices, DynamicBuffer<MeshNode> nodes, DynamicBuffer<ProceduralBone> prefabBones, DynamicBuffer<Bone> bones, Skeleton skeleton, int2 elementIndex, ref RaycastHit hit)
	{
		bool result = false;
		int* ptr = stackalloc int[128];
		for (int i = 0; i < prefabBones.Length; i++)
		{
			int num = 0;
			Line3.Segment line = default(Line3.Segment);
			ProceduralBone proceduralBone = prefabBones[i];
			if (math.any(MathUtils.Size(nodes[proceduralBone.m_BindIndex].m_Bounds) > 0f))
			{
				ptr[num++] = proceduralBone.m_BindIndex;
				Bone bone = bones[skeleton.m_BoneOffset + i];
				float4x4 float4x = float4x4.TRS(bone.m_Position, bone.m_Rotation, bone.m_Scale);
				int parentIndex = proceduralBone.m_ParentIndex;
				while (parentIndex >= 0)
				{
					Bone bone2 = bones[skeleton.m_BoneOffset + parentIndex];
					ProceduralBone proceduralBone2 = prefabBones[parentIndex];
					float4x = math.mul(float4x4.TRS(bone2.m_Position, bone2.m_Rotation, bone2.m_Scale), float4x);
					parentIndex = proceduralBone2.m_ParentIndex;
				}
				float4x = math.mul(float4x, proceduralBone.m_BindPose);
				float4x = math.inverse(float4x);
				line.a = math.mul(float4x, new float4(localLine.a, 1f)).xyz;
				line.b = math.mul(float4x, new float4(localLine.b, 1f)).xyz;
			}
			while (--num >= 0)
			{
				int index = ptr[num];
				MeshNode meshNode = nodes[index];
				if (!MathUtils.Intersect(meshNode.m_Bounds, line, out var _))
				{
					continue;
				}
				for (int j = meshNode.m_IndexRange.x; j < meshNode.m_IndexRange.y; j += 3)
				{
					Triangle3 triangle = new Triangle3(vertices[indices[j].m_Index].m_Vertex, vertices[indices[j + 1].m_Index].m_Vertex, vertices[indices[j + 2].m_Index].m_Vertex);
					if (MathUtils.Intersect(triangle, line, out var t2) && t2.z < hit.m_NormalizedDistance)
					{
						hit.m_HitDirection = MathUtils.NormalCW(triangle);
						hit.m_NormalizedDistance = t2.z;
						hit.m_CellIndex = elementIndex;
						result = true;
					}
				}
				ptr[num] = meshNode.m_SubNodes1.x;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.x != -1);
				ptr[num] = meshNode.m_SubNodes1.y;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.y != -1);
				ptr[num] = meshNode.m_SubNodes1.z;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.z != -1);
				ptr[num] = meshNode.m_SubNodes1.w;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.w != -1);
				ptr[num] = meshNode.m_SubNodes2.x;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.x != -1);
				ptr[num] = meshNode.m_SubNodes2.y;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.y != -1);
				ptr[num] = meshNode.m_SubNodes2.z;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.z != -1);
				ptr[num] = meshNode.m_SubNodes2.w;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.w != -1);
			}
		}
		return result;
	}
```

- `private static CheckMeshIntersect(Colossal.Mathematics.Line3+Segment localLine, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Mathematics.int2 elementIndex, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
private unsafe static bool CheckMeshIntersect(Line3.Segment localLine, DynamicBuffer<MeshVertex> vertices, DynamicBuffer<MeshIndex> indices, DynamicBuffer<MeshNode> nodes, DynamicBuffer<ProceduralBone> prefabBones, DynamicBuffer<Bone> bones, Skeleton skeleton, int2 elementIndex, ref RaycastHit hit)
	{
		bool result = false;
		int* ptr = stackalloc int[128];
		for (int i = 0; i < prefabBones.Length; i++)
		{
			int num = 0;
			Line3.Segment line = default(Line3.Segment);
			ProceduralBone proceduralBone = prefabBones[i];
			if (math.any(MathUtils.Size(nodes[proceduralBone.m_BindIndex].m_Bounds) > 0f))
			{
				ptr[num++] = proceduralBone.m_BindIndex;
				Bone bone = bones[skeleton.m_BoneOffset + i];
				float4x4 float4x = float4x4.TRS(bone.m_Position, bone.m_Rotation, bone.m_Scale);
				int parentIndex = proceduralBone.m_ParentIndex;
				while (parentIndex >= 0)
				{
					Bone bone2 = bones[skeleton.m_BoneOffset + parentIndex];
					ProceduralBone proceduralBone2 = prefabBones[parentIndex];
					float4x = math.mul(float4x4.TRS(bone2.m_Position, bone2.m_Rotation, bone2.m_Scale), float4x);
					parentIndex = proceduralBone2.m_ParentIndex;
				}
				float4x = math.mul(float4x, proceduralBone.m_BindPose);
				float4x = math.inverse(float4x);
				line.a = math.mul(float4x, new float4(localLine.a, 1f)).xyz;
				line.b = math.mul(float4x, new float4(localLine.b, 1f)).xyz;
			}
			while (--num >= 0)
			{
				int index = ptr[num];
				MeshNode meshNode = nodes[index];
				if (!MathUtils.Intersect(meshNode.m_Bounds, line, out var _))
				{
					continue;
				}
				for (int j = meshNode.m_IndexRange.x; j < meshNode.m_IndexRange.y; j += 3)
				{
					Triangle3 triangle = new Triangle3(vertices[indices[j].m_Index].m_Vertex, vertices[indices[j + 1].m_Index].m_Vertex, vertices[indices[j + 2].m_Index].m_Vertex);
					if (MathUtils.Intersect(triangle, line, out var t2) && t2.z < hit.m_NormalizedDistance)
					{
						hit.m_HitDirection = MathUtils.NormalCW(triangle);
						hit.m_NormalizedDistance = t2.z;
						hit.m_CellIndex = elementIndex;
						result = true;
					}
				}
				ptr[num] = meshNode.m_SubNodes1.x;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.x != -1);
				ptr[num] = meshNode.m_SubNodes1.y;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.y != -1);
				ptr[num] = meshNode.m_SubNodes1.z;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.z != -1);
				ptr[num] = meshNode.m_SubNodes1.w;
				num = math.select(num, num + 1, meshNode.m_SubNodes1.w != -1);
				ptr[num] = meshNode.m_SubNodes2.x;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.x != -1);
				ptr[num] = meshNode.m_SubNodes2.y;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.y != -1);
				ptr[num] = meshNode.m_SubNodes2.z;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.z != -1);
				ptr[num] = meshNode.m_SubNodes2.w;
				num = math.select(num, num + 1, meshNode.m_SubNodes2.w != -1);
			}
		}
		return result;
	}
```


## Nested types

- `Game.Objects.RaycastJobs+RaycastStaticObjectsJob`  
- `Game.Objects.RaycastJobs+GetSourceRangesJob`  
- `Game.Objects.RaycastJobs+ExtractLaneObjectsJob`  
- `Game.Objects.RaycastJobs+RaycastMovingObjectsJob`  

