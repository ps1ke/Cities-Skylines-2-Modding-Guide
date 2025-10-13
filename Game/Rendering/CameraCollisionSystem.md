# Game.Rendering.CameraCollisionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CameraCollisionSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Mathematics.float3 m_PreviousPosition;
    private Unity.Mathematics.quaternion m_Rotation;
    private System.Single m_MaxForwardOffset;
    private System.Single m_MaxBackwardOffset;
    private System.Single m_MinClearDistance;
    private System.Single m_NearPlane;
    private System.Single m_Smoothing;
    private Unity.Mathematics.float2 m_FieldOfView;
    private Unity.Collections.NativeReference<Game.Rendering.CameraCollisionSystem+Result> m_Result;
    private Game.Rendering.CameraCollisionSystem+TypeHandle __TypeHandle;

    public CameraCollisionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void CheckCollisions(Unity.Mathematics.float3& position, Unity.Mathematics.float3 previousPosition, Unity.Mathematics.quaternion rotation, System.Single maxForwardOffset, System.Single maxBackwardOffset, System.Single minClearDistance, System.Single nearPlane, System.Single smoothing, Unity.Mathematics.float2 fieldOfView);
    private static System.Void CheckCollisions(Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions, System.Single minClearRange, Unity.Mathematics.float2 limits);
    private static System.Void CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions);
    private static System.Void CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions);
    private static System.Void CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions);
    private static System.Void CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions);
    private static System.Void CheckTriangleIntersect(Game.Rendering.CameraCollisionSystem+Line line, Colossal.Mathematics.Triangle3 triangle, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions);
    private static System.Boolean Intersect(Game.Rendering.CameraCollisionSystem+Line line, Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float2& t);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Mathematics.float3 m_PreviousPosition`  

```csharp
private Unity.Mathematics.float3 m_PreviousPosition;
```

- `private Unity.Mathematics.quaternion m_Rotation`  

```csharp
private Unity.Mathematics.quaternion m_Rotation;
```

- `private System.Single m_MaxForwardOffset`  

```csharp
private System.Single m_MaxForwardOffset;
```

- `private System.Single m_MaxBackwardOffset`  

```csharp
private System.Single m_MaxBackwardOffset;
```

- `private System.Single m_MinClearDistance`  

```csharp
private System.Single m_MinClearDistance;
```

- `private System.Single m_NearPlane`  

```csharp
private System.Single m_NearPlane;
```

- `private System.Single m_Smoothing`  

```csharp
private System.Single m_Smoothing;
```

- `private Unity.Mathematics.float2 m_FieldOfView`  

```csharp
private Unity.Mathematics.float2 m_FieldOfView;
```

- `private Unity.Collections.NativeReference<Game.Rendering.CameraCollisionSystem+Result> m_Result`  

```csharp
private Unity.Collections.NativeReference<Game.Rendering.CameraCollisionSystem+Result> m_Result;
```

- `private Game.Rendering.CameraCollisionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.CameraCollisionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CameraCollisionSystem()`  

```csharp
[Preserve]
	public CameraCollisionSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public CheckCollisions(Unity.Mathematics.float3& position, Unity.Mathematics.float3 previousPosition, Unity.Mathematics.quaternion rotation, System.Single maxForwardOffset, System.Single maxBackwardOffset, System.Single minClearDistance, System.Single nearPlane, System.Single smoothing, Unity.Mathematics.float2 fieldOfView) : System.Void`  

```csharp
private static void CheckCollisions(NativeList<Collision> collisions, float minClearRange, float2 limits)
	{
		if (collisions.Length == 0)
		{
			return;
		}
		collisions.Sort();
		int num = 0;
		Collision value = collisions[0];
		for (int i = 1; i < collisions.Length; i++)
		{
			Collision collision = collisions[i];
			if (collision.m_LineBounds.min - value.m_LineBounds.max < minClearRange)
			{
				value.m_LineBounds.max = math.max(value.m_LineBounds.max, collision.m_LineBounds.max);
				value.m_CoverAreas += collision.m_CoverAreas;
				value.m_StartEnd |= collision.m_StartEnd;
			}
			else
			{
				value.m_StartEnd &= value.m_CoverAreas >= value.m_CoverAreas.yx * 0.5f;
				collisions[num++] = value;
				value = collision;
			}
		}
		value.m_StartEnd &= value.m_CoverAreas >= value.m_CoverAreas.yx * 0.5f;
		collisions[num++] = value;
		collisions.RemoveRange(num, collisions.Length - num);
		num = 0;
		value = collisions[0];
		if (!value.m_StartEnd.x)
		{
			value.m_LineBounds.min = math.min(value.m_LineBounds.min, limits.x);
			value.m_StartEnd.x = true;
		}
		for (int j = 1; j < collisions.Length; j++)
		{
			Collision collision2 = collisions[j];
			if (!value.m_StartEnd.y || !collision2.m_StartEnd.x)
			{
				value.m_LineBounds.max = collision2.m_LineBounds.max;
				value.m_CoverAreas += collision2.m_CoverAreas;
				value.m_StartEnd.y = collision2.m_StartEnd.y;
			}
			else
			{
				collisions[num++] = value;
				value = collision2;
			}
		}
		if (!value.m_StartEnd.y)
		{
			value.m_LineBounds.max = math.max(value.m_LineBounds.max, limits.y);
			value.m_StartEnd.y = true;
		}
		collisions[num++] = value;
		collisions.RemoveRange(num, collisions.Length - num);
	}
```

- `private static CheckCollisions(Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions, System.Single minClearRange, Unity.Mathematics.float2 limits) : System.Void`  

```csharp
private static void CheckCollisions(NativeList<Collision> collisions, float minClearRange, float2 limits)
	{
		if (collisions.Length == 0)
		{
			return;
		}
		collisions.Sort();
		int num = 0;
		Collision value = collisions[0];
		for (int i = 1; i < collisions.Length; i++)
		{
			Collision collision = collisions[i];
			if (collision.m_LineBounds.min - value.m_LineBounds.max < minClearRange)
			{
				value.m_LineBounds.max = math.max(value.m_LineBounds.max, collision.m_LineBounds.max);
				value.m_CoverAreas += collision.m_CoverAreas;
				value.m_StartEnd |= collision.m_StartEnd;
			}
			else
			{
				value.m_StartEnd &= value.m_CoverAreas >= value.m_CoverAreas.yx * 0.5f;
				collisions[num++] = value;
				value = collision;
			}
		}
		value.m_StartEnd &= value.m_CoverAreas >= value.m_CoverAreas.yx * 0.5f;
		collisions[num++] = value;
		collisions.RemoveRange(num, collisions.Length - num);
		num = 0;
		value = collisions[0];
		if (!value.m_StartEnd.x)
		{
			value.m_LineBounds.min = math.min(value.m_LineBounds.min, limits.x);
			value.m_StartEnd.x = true;
		}
		for (int j = 1; j < collisions.Length; j++)
		{
			Collision collision2 = collisions[j];
			if (!value.m_StartEnd.y || !collision2.m_StartEnd.x)
			{
				value.m_LineBounds.max = collision2.m_LineBounds.max;
				value.m_CoverAreas += collision2.m_CoverAreas;
				value.m_StartEnd.y = collision2.m_StartEnd.y;
			}
			else
			{
				collisions[num++] = value;
				value = collision2;
			}
		}
		if (!value.m_StartEnd.y)
		{
			value.m_LineBounds.max = math.max(value.m_LineBounds.max, limits.y);
			value.m_StartEnd.y = true;
		}
		collisions[num++] = value;
		collisions.RemoveRange(num, collisions.Length - num);
	}
```

- `private static CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  

```csharp
private unsafe static void CheckMeshIntersect(Line line, DynamicBuffer<MeshVertex> vertices, DynamicBuffer<MeshIndex> indices, DynamicBuffer<MeshNode> nodes, DynamicBuffer<ProceduralBone> prefabBones, DynamicBuffer<Bone> bones, Skeleton skeleton, NativeList<Collision> collisions)
	{
		int* ptr = stackalloc int[128];
		for (int i = 0; i < prefabBones.Length; i++)
		{
			int num = 0;
			Line line2 = line;
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
				line2.m_Line.a = math.mul(float4x, new float4(line.m_Line.a, 1f)).xyz;
				line2.m_Line.b = math.mul(float4x, new float4(line.m_Line.b, 1f)).xyz;
				line2.m_XVector = math.mul(float4x, new float4(line.m_XVector, 0f)).xyz;
				line2.m_YVector = math.mul(float4x, new float4(line.m_YVector, 0f)).xyz;
				line2.m_Expand = math.abs(line2.m_XVector) + math.abs(line2.m_YVector);
			}
			while (--num >= 0)
			{
				int index = ptr[num];
				MeshNode meshNode = nodes[index];
				if (Intersect(line2, meshNode.m_Bounds, out var _))
				{
					for (int j = meshNode.m_IndexRange.x; j < meshNode.m_IndexRange.y; j += 3)
					{
						CheckTriangleIntersect(triangle: new Triangle3(vertices[indices[j].m_Index].m_Vertex, vertices[indices[j + 1].m_Index].m_Vertex, vertices[indices[j + 2].m_Index].m_Vertex), line: line2, collisions: collisions);
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
		}
	}
```

- `private static CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  

```csharp
private unsafe static void CheckMeshIntersect(Line line, DynamicBuffer<MeshVertex> vertices, DynamicBuffer<MeshIndex> indices, DynamicBuffer<MeshNode> nodes, DynamicBuffer<ProceduralBone> prefabBones, DynamicBuffer<Bone> bones, Skeleton skeleton, NativeList<Collision> collisions)
	{
		int* ptr = stackalloc int[128];
		for (int i = 0; i < prefabBones.Length; i++)
		{
			int num = 0;
			Line line2 = line;
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
				line2.m_Line.a = math.mul(float4x, new float4(line.m_Line.a, 1f)).xyz;
				line2.m_Line.b = math.mul(float4x, new float4(line.m_Line.b, 1f)).xyz;
				line2.m_XVector = math.mul(float4x, new float4(line.m_XVector, 0f)).xyz;
				line2.m_YVector = math.mul(float4x, new float4(line.m_YVector, 0f)).xyz;
				line2.m_Expand = math.abs(line2.m_XVector) + math.abs(line2.m_YVector);
			}
			while (--num >= 0)
			{
				int index = ptr[num];
				MeshNode meshNode = nodes[index];
				if (Intersect(line2, meshNode.m_Bounds, out var _))
				{
					for (int j = meshNode.m_IndexRange.x; j < meshNode.m_IndexRange.y; j += 3)
					{
						CheckTriangleIntersect(triangle: new Triangle3(vertices[indices[j].m_Index].m_Vertex, vertices[indices[j + 1].m_Index].m_Vertex, vertices[indices[j + 2].m_Index].m_Vertex), line: line2, collisions: collisions);
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
		}
	}
```

- `private static CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  

```csharp
private unsafe static void CheckMeshIntersect(Line line, DynamicBuffer<MeshVertex> vertices, DynamicBuffer<MeshIndex> indices, DynamicBuffer<MeshNode> nodes, DynamicBuffer<ProceduralBone> prefabBones, DynamicBuffer<Bone> bones, Skeleton skeleton, NativeList<Collision> collisions)
	{
		int* ptr = stackalloc int[128];
		for (int i = 0; i < prefabBones.Length; i++)
		{
			int num = 0;
			Line line2 = line;
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
				line2.m_Line.a = math.mul(float4x, new float4(line.m_Line.a, 1f)).xyz;
				line2.m_Line.b = math.mul(float4x, new float4(line.m_Line.b, 1f)).xyz;
				line2.m_XVector = math.mul(float4x, new float4(line.m_XVector, 0f)).xyz;
				line2.m_YVector = math.mul(float4x, new float4(line.m_YVector, 0f)).xyz;
				line2.m_Expand = math.abs(line2.m_XVector) + math.abs(line2.m_YVector);
			}
			while (--num >= 0)
			{
				int index = ptr[num];
				MeshNode meshNode = nodes[index];
				if (Intersect(line2, meshNode.m_Bounds, out var _))
				{
					for (int j = meshNode.m_IndexRange.x; j < meshNode.m_IndexRange.y; j += 3)
					{
						CheckTriangleIntersect(triangle: new Triangle3(vertices[indices[j].m_Index].m_Vertex, vertices[indices[j + 1].m_Index].m_Vertex, vertices[indices[j + 2].m_Index].m_Vertex), line: line2, collisions: collisions);
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
		}
	}
```

- `private static CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  

```csharp
private unsafe static void CheckMeshIntersect(Line line, DynamicBuffer<MeshVertex> vertices, DynamicBuffer<MeshIndex> indices, DynamicBuffer<MeshNode> nodes, DynamicBuffer<ProceduralBone> prefabBones, DynamicBuffer<Bone> bones, Skeleton skeleton, NativeList<Collision> collisions)
	{
		int* ptr = stackalloc int[128];
		for (int i = 0; i < prefabBones.Length; i++)
		{
			int num = 0;
			Line line2 = line;
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
				line2.m_Line.a = math.mul(float4x, new float4(line.m_Line.a, 1f)).xyz;
				line2.m_Line.b = math.mul(float4x, new float4(line.m_Line.b, 1f)).xyz;
				line2.m_XVector = math.mul(float4x, new float4(line.m_XVector, 0f)).xyz;
				line2.m_YVector = math.mul(float4x, new float4(line.m_YVector, 0f)).xyz;
				line2.m_Expand = math.abs(line2.m_XVector) + math.abs(line2.m_YVector);
			}
			while (--num >= 0)
			{
				int index = ptr[num];
				MeshNode meshNode = nodes[index];
				if (Intersect(line2, meshNode.m_Bounds, out var _))
				{
					for (int j = meshNode.m_IndexRange.x; j < meshNode.m_IndexRange.y; j += 3)
					{
						CheckTriangleIntersect(triangle: new Triangle3(vertices[indices[j].m_Index].m_Vertex, vertices[indices[j + 1].m_Index].m_Vertex, vertices[indices[j + 2].m_Index].m_Vertex), line: line2, collisions: collisions);
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
		}
	}
```

- `private static CheckTriangleIntersect(Game.Rendering.CameraCollisionSystem+Line line, Colossal.Mathematics.Triangle3 triangle, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  

```csharp
private static void CheckTriangleIntersect(Line line, Triangle3 triangle, NativeList<Collision> collisions)
	{
		triangle *= line.m_Scale;
		if (!MathUtils.Intersect(MathUtils.Expand(MathUtils.Bounds(triangle), line.m_Expand), line.m_Line, out var _))
		{
			return;
		}
		float3 x = triangle.a - line.m_Line.a;
		float3 x2 = triangle.b - line.m_Line.a;
		float3 x3 = triangle.c - line.m_Line.a;
		Bounds2 bounds = default(Bounds2);
		bounds.max = new float2(math.lengthsq(line.m_XVector), math.lengthsq(line.m_YVector));
		bounds.min = -bounds.max;
		Triangle2 triangle2 = default(Triangle2);
		triangle2.a = new float2(math.dot(x, line.m_XVector), math.dot(x, line.m_YVector));
		triangle2.b = new float2(math.dot(x2, line.m_XVector), math.dot(x2, line.m_YVector));
		triangle2.c = new float2(math.dot(x3, line.m_XVector), math.dot(x3, line.m_YVector));
		if (!MathUtils.Intersect(bounds, triangle2, out var area))
		{
			return;
		}
		float3 @float = line.m_Line.b - line.m_Line.a;
		float3 y = @float * (1f / math.lengthsq(@float));
		Triangle1 triangle3 = default(Triangle1);
		triangle3.a = math.dot(x, y);
		triangle3.b = math.dot(x2, y);
		triangle3.c = math.dot(x3, y);
		Bounds1 bounds2 = new Bounds1(float.MaxValue, float.MinValue);
		if (MathUtils.Intersect(bounds, triangle2.ab, out var t2))
		{
			t2 = math.lerp(triangle3.a, triangle3.b, t2);
			bounds2.min = math.min(bounds2.min, math.cmin(t2));
			bounds2.max = math.max(bounds2.max, math.cmax(t2));
		}
		if (MathUtils.Intersect(bounds, triangle2.bc, out t2))
		{
			t2 = math.lerp(triangle3.b, triangle3.c, t2);
			bounds2.min = math.min(bounds2.min, math.cmin(t2));
			bounds2.max = math.max(bounds2.max, math.cmax(t2));
		}
		if (MathUtils.Intersect(bounds, triangle2.ca, out t2))
		{
			t2 = math.lerp(triangle3.c, triangle3.a, t2);
			bounds2.min = math.min(bounds2.min, math.cmin(t2));
			bounds2.max = math.max(bounds2.max, math.cmax(t2));
		}
		if (MathUtils.Intersect(triangle2, bounds.min, out t2))
		{
			bounds2 |= MathUtils.Position(triangle3, t2);
		}
		if (MathUtils.Intersect(triangle2, new float2(bounds.max.x, bounds.min.y), out t2))
		{
			bounds2 |= MathUtils.Position(triangle3, t2);
		}
		if (MathUtils.Intersect(triangle2, new float2(bounds.min.x, bounds.max.y), out t2))
		{
			bounds2 |= MathUtils.Position(triangle3, t2);
		}
		if (MathUtils.Intersect(triangle2, bounds.max, out t2))
		{
			bounds2 |= MathUtils.Position(triangle3, t2);
		}
		if (bounds2.min <= 1f && bounds2.max >= 0f)
		{
			Collision value = default(Collision);
			value.m_LineBounds.min = math.lerp(line.m_CutOffset.x, line.m_CutOffset.y, bounds2.min);
			value.m_LineBounds.max = math.lerp(line.m_CutOffset.x, line.m_CutOffset.y, bounds2.max);
			if (MathUtils.IsClockwise(triangle2))
			{
				value.m_CoverAreas = new float2(area, 0f);
				value.m_StartEnd = new bool2(x: true, y: false);
			}
			else
			{
				value.m_CoverAreas = new float2(0f, area);
				value.m_StartEnd = new bool2(x: false, y: true);
			}
			collisions.Add(in value);
		}
	}
```

- `private static Intersect(Game.Rendering.CameraCollisionSystem+Line line, Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
private static bool Intersect(Line line, Bounds3 bounds, out float2 t)
	{
		bounds = MathUtils.Expand(bounds, line.m_Expand) * line.m_Scale;
		return MathUtils.Intersect(bounds, line.m_Line, out t);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_Result = new NativeReference<Result>(Allocator.Persistent);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Result.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		float3 @float = m_Result.Value.m_Position;
		float3 float2 = math.forward(m_Rotation);
		float num = m_MaxForwardOffset + m_MinClearDistance;
		float num2 = m_MaxBackwardOffset;
		Line3.Segment line = new Line3.Segment(@float - float2 * num2, @float + float2 * num);
		float2 fovOffset = math.tan(math.radians(m_FieldOfView) * 0.5f) * m_MinClearDistance;
		float minClearRange = m_MinClearDistance / (num + num2);
		float nearPlaneRange = m_NearPlane / (num + num2);
		NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
		NativeQueue<Collision> collisions = new NativeQueue<Collision>(Allocator.TempJob);
		JobHandle dependencies;
		FindEntitiesFromTreeJob jobData = new FindEntitiesFromTreeJob
		{
			m_Line = line,
			m_Rotation = m_Rotation,
			m_FovOffset = fovOffset,
			m_SearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_EntityList = nativeList
		};
		ObjectCollisionJob jobData2 = new ObjectCollisionJob
		{
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_NetObject_RO_ComponentLookup, ref base.CheckedStateRef),
			m_QuantityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Quantity_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnderConstructionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabImpostorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ImpostorData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSharedMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SharedMeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGrowthScaleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GrowthScaleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabQuantityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_QuantityObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_Skeletons = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RO_BufferLookup, ref base.CheckedStateRef),
			m_Bones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Bone_RO_BufferLookup, ref base.CheckedStateRef),
			m_Meshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_Lods = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LodMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_Vertices = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_MeshVertex_RO_BufferLookup, ref base.CheckedStateRef),
			m_Indices = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_MeshIndex_RO_BufferLookup, ref base.CheckedStateRef),
			m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_MeshNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralBones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RO_BufferLookup, ref base.CheckedStateRef),
			m_Line = line,
			m_Rotation = m_Rotation,
			m_FovOffset = fovOffset,
			m_MinClearRange = minClearRange,
			m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_EntityList = nativeList,
			m_Collisions = collisions.AsParallelWriter()
		};
		JobHandle deps;
		SelectCameraPositionJob jobData3 = new SelectCameraPositionJob
		{
			m_Line = line,
			m_PreviousPosition = m_PreviousPosition,
			m_MinClearRange = minClearRange,
			m_NearPlaneRange = nearPlaneRange,
			m_Smoothing = m_Smoothing,
			m_DeltaTime = UnityEngine.Time.deltaTime,
			m_TerrainData = m_TerrainSystem.GetHeightData(),
			m_WaterData = m_WaterSystem.GetSurfaceData(out deps),
			m_Collisions = collisions,
			m_Result = m_Result
		};
		JobHandle jobHandle = IJobExtensions.Schedule(jobData, dependencies);
		JobHandle jobHandle2 = jobData2.Schedule(nativeList, 1, JobHandle.CombineDependencies(base.Dependency, jobHandle));
		JobHandle jobHandle3 = IJobExtensions.Schedule(jobData3, JobHandle.CombineDependencies(jobHandle2, deps));
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle3);
		m_WaterSystem.AddSurfaceReader(jobHandle3);
		nativeList.Dispose(jobHandle2);
		collisions.Dispose(jobHandle3);
		jobHandle3.Complete();
	}
```


## Nested types

- `Game.Rendering.CameraCollisionSystem+FindEntitiesFromTreeJob`  
- `Game.Rendering.CameraCollisionSystem+ObjectCollisionJob`  
- `Game.Rendering.CameraCollisionSystem+SelectCameraPositionJob`  
- `Game.Rendering.CameraCollisionSystem+Line`  
- `Game.Rendering.CameraCollisionSystem+Collision`  
- `Game.Rendering.CameraCollisionSystem+Result`  
- `Game.Rendering.CameraCollisionSystem+TypeHandle`  

