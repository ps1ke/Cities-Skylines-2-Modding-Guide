# Game.Tools.ClearAreaHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ClearAreaHelpers
{
    public static System.Void FillClearAreas(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.Entity ignoreUpgradeOrArea, Unity.Entities.ComponentLookup<Game.Objects.Transform> transformData, Unity.Entities.ComponentLookup<Game.Areas.Clear> clearAreaData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.BufferLookup<Game.Areas.SubArea> subAreaBuffers, Unity.Entities.BufferLookup<Game.Areas.Node> nodeBuffers, Unity.Entities.BufferLookup<Game.Areas.Triangle> triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
    public static System.Void FillClearAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Game.Objects.Transform transform, Game.Prefabs.ObjectGeometryData objectGeometryData, Unity.Entities.Entity ignoreArea, Unity.Entities.ComponentLookup`1[[Game.Areas.Clear, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreaData, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeBuffers, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
    public static System.Void FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> prefabAreaGeometryData, Unity.Entities.BufferLookup<Game.Prefabs.SubArea> prefabSubAreas, Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> prefabSubAreaNodes, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
    public static System.Void FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Boolean isComplete, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
    public static System.Void InitClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform topLevelTransform);
    public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Mathematics.float3 position, System.Boolean onGround);
    public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Bezier4x3 curve, System.Boolean onGround);
    public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Game.Objects.Transform ownerTransform);
    public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodes, Unity.Mathematics.int2 nodeRange, Game.Objects.Transform ownerTransform);
    private static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Triangle3 triangle, Game.Objects.Transform ownerTransform);
    public static System.Void TransformClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform oldTransform, Game.Objects.Transform newTransform);
}
```


## Methods

- `public static FillClearAreas(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.Entity ignoreUpgradeOrArea, Unity.Entities.ComponentLookup<Game.Objects.Transform> transformData, Unity.Entities.ComponentLookup<Game.Areas.Clear> clearAreaData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.BufferLookup<Game.Areas.SubArea> subAreaBuffers, Unity.Entities.BufferLookup<Game.Areas.Node> nodeBuffers, Unity.Entities.BufferLookup<Game.Areas.Triangle> triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas) : System.Void`  

```csharp
public static void FillClearAreas(Entity ownerPrefab, Transform ownerTransform, DynamicBuffer<Node> nodes, bool isComplete, ComponentLookup<ObjectGeometryData> prefabObjectGeometryData, ref NativeList<ClearAreaData> clearAreas)
	{
		int num = nodes.Length;
		if (num >= 3)
		{
			if (num >= 4 && nodes[0].m_Position.Equals(nodes[num - 1].m_Position))
			{
				isComplete = true;
				num--;
			}
			if (!clearAreas.IsCreated)
			{
				clearAreas = new NativeList<ClearAreaData>(16, Allocator.Temp);
			}
			NativeArray<float3> nodes2 = new NativeArray<float3>(num, Allocator.Temp);
			NativeList<Triangle> triangles = new NativeList<Triangle>(Allocator.Temp);
			bool isCounterClockwise = GeometrySystem.Area(nodes) > 0f;
			for (int i = 0; i < num; i++)
			{
				nodes2[i] = AreaUtils.GetExpandedNode(nodes, i, -0.1f, isComplete, isCounterClockwise);
			}
			GeometrySystem.Triangulate(nodes2, triangles, default(NativeArray<Bounds2>), 0, isCounterClockwise);
			GeometrySystem.EqualizeTriangles(nodes2, triangles);
			ObjectGeometryData objectGeometryData = prefabObjectGeometryData[ownerPrefab];
			float topY = ownerTransform.m_Position.y + objectGeometryData.m_Bounds.max.y + 1f;
			for (int j = 0; j < triangles.Length; j++)
			{
				clearAreas.Add(new ClearAreaData
				{
					m_Triangle = AreaUtils.GetTriangle3(nodes, triangles[j]),
					m_TopY = topY
				});
			}
			nodes2.Dispose();
			triangles.Dispose();
		}
	}
```

- `public static FillClearAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Game.Objects.Transform transform, Game.Prefabs.ObjectGeometryData objectGeometryData, Unity.Entities.Entity ignoreArea, Unity.Entities.ComponentLookup`1[[Game.Areas.Clear, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreaData, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeBuffers, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas) : System.Void`  

```csharp
public static void FillClearAreas(Entity ownerPrefab, Transform ownerTransform, DynamicBuffer<Node> nodes, bool isComplete, ComponentLookup<ObjectGeometryData> prefabObjectGeometryData, ref NativeList<ClearAreaData> clearAreas)
	{
		int num = nodes.Length;
		if (num >= 3)
		{
			if (num >= 4 && nodes[0].m_Position.Equals(nodes[num - 1].m_Position))
			{
				isComplete = true;
				num--;
			}
			if (!clearAreas.IsCreated)
			{
				clearAreas = new NativeList<ClearAreaData>(16, Allocator.Temp);
			}
			NativeArray<float3> nodes2 = new NativeArray<float3>(num, Allocator.Temp);
			NativeList<Triangle> triangles = new NativeList<Triangle>(Allocator.Temp);
			bool isCounterClockwise = GeometrySystem.Area(nodes) > 0f;
			for (int i = 0; i < num; i++)
			{
				nodes2[i] = AreaUtils.GetExpandedNode(nodes, i, -0.1f, isComplete, isCounterClockwise);
			}
			GeometrySystem.Triangulate(nodes2, triangles, default(NativeArray<Bounds2>), 0, isCounterClockwise);
			GeometrySystem.EqualizeTriangles(nodes2, triangles);
			ObjectGeometryData objectGeometryData = prefabObjectGeometryData[ownerPrefab];
			float topY = ownerTransform.m_Position.y + objectGeometryData.m_Bounds.max.y + 1f;
			for (int j = 0; j < triangles.Length; j++)
			{
				clearAreas.Add(new ClearAreaData
				{
					m_Triangle = AreaUtils.GetTriangle3(nodes, triangles[j]),
					m_TopY = topY
				});
			}
			nodes2.Dispose();
			triangles.Dispose();
		}
	}
```

- `public static FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> prefabAreaGeometryData, Unity.Entities.BufferLookup<Game.Prefabs.SubArea> prefabSubAreas, Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> prefabSubAreaNodes, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas) : System.Void`  

```csharp
public static void FillClearAreas(Entity ownerPrefab, Transform ownerTransform, DynamicBuffer<Node> nodes, bool isComplete, ComponentLookup<ObjectGeometryData> prefabObjectGeometryData, ref NativeList<ClearAreaData> clearAreas)
	{
		int num = nodes.Length;
		if (num >= 3)
		{
			if (num >= 4 && nodes[0].m_Position.Equals(nodes[num - 1].m_Position))
			{
				isComplete = true;
				num--;
			}
			if (!clearAreas.IsCreated)
			{
				clearAreas = new NativeList<ClearAreaData>(16, Allocator.Temp);
			}
			NativeArray<float3> nodes2 = new NativeArray<float3>(num, Allocator.Temp);
			NativeList<Triangle> triangles = new NativeList<Triangle>(Allocator.Temp);
			bool isCounterClockwise = GeometrySystem.Area(nodes) > 0f;
			for (int i = 0; i < num; i++)
			{
				nodes2[i] = AreaUtils.GetExpandedNode(nodes, i, -0.1f, isComplete, isCounterClockwise);
			}
			GeometrySystem.Triangulate(nodes2, triangles, default(NativeArray<Bounds2>), 0, isCounterClockwise);
			GeometrySystem.EqualizeTriangles(nodes2, triangles);
			ObjectGeometryData objectGeometryData = prefabObjectGeometryData[ownerPrefab];
			float topY = ownerTransform.m_Position.y + objectGeometryData.m_Bounds.max.y + 1f;
			for (int j = 0; j < triangles.Length; j++)
			{
				clearAreas.Add(new ClearAreaData
				{
					m_Triangle = AreaUtils.GetTriangle3(nodes, triangles[j]),
					m_TopY = topY
				});
			}
			nodes2.Dispose();
			triangles.Dispose();
		}
	}
```

- `public static FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Boolean isComplete, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas) : System.Void`  

```csharp
public static void FillClearAreas(Entity ownerPrefab, Transform ownerTransform, DynamicBuffer<Node> nodes, bool isComplete, ComponentLookup<ObjectGeometryData> prefabObjectGeometryData, ref NativeList<ClearAreaData> clearAreas)
	{
		int num = nodes.Length;
		if (num >= 3)
		{
			if (num >= 4 && nodes[0].m_Position.Equals(nodes[num - 1].m_Position))
			{
				isComplete = true;
				num--;
			}
			if (!clearAreas.IsCreated)
			{
				clearAreas = new NativeList<ClearAreaData>(16, Allocator.Temp);
			}
			NativeArray<float3> nodes2 = new NativeArray<float3>(num, Allocator.Temp);
			NativeList<Triangle> triangles = new NativeList<Triangle>(Allocator.Temp);
			bool isCounterClockwise = GeometrySystem.Area(nodes) > 0f;
			for (int i = 0; i < num; i++)
			{
				nodes2[i] = AreaUtils.GetExpandedNode(nodes, i, -0.1f, isComplete, isCounterClockwise);
			}
			GeometrySystem.Triangulate(nodes2, triangles, default(NativeArray<Bounds2>), 0, isCounterClockwise);
			GeometrySystem.EqualizeTriangles(nodes2, triangles);
			ObjectGeometryData objectGeometryData = prefabObjectGeometryData[ownerPrefab];
			float topY = ownerTransform.m_Position.y + objectGeometryData.m_Bounds.max.y + 1f;
			for (int j = 0; j < triangles.Length; j++)
			{
				clearAreas.Add(new ClearAreaData
				{
					m_Triangle = AreaUtils.GetTriangle3(nodes, triangles[j]),
					m_TopY = topY
				});
			}
			nodes2.Dispose();
			triangles.Dispose();
		}
	}
```

- `public static InitClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform topLevelTransform) : System.Void`  

```csharp
public static void InitClearAreas(NativeList<ClearAreaData> clearAreas, Transform topLevelTransform)
	{
		if (clearAreas.IsCreated)
		{
			for (int i = 0; i < clearAreas.Length; i++)
			{
				ClearAreaData value = clearAreas[i];
				value.m_OnGround = math.any(math.abs(value.m_Triangle.y.abc - topLevelTransform.m_Position.y) <= 1f);
				value.m_Triangle.y -= 1f;
				clearAreas[i] = value;
			}
		}
	}
```

- `public static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Mathematics.float3 position, System.Boolean onGround) : System.Boolean`  

```csharp
private static bool ShouldClear(NativeList<ClearAreaData> clearAreas, Triangle3 triangle, Transform ownerTransform)
	{
		Bounds3 bounds = MathUtils.Bounds(triangle);
		bool flag = math.any(math.abs(triangle.y.abc - ownerTransform.m_Position.y) <= 1f);
		for (int i = 0; i < clearAreas.Length; i++)
		{
			ClearAreaData clearAreaData = clearAreas[i];
			Bounds3 bounds2 = MathUtils.Bounds(clearAreaData.m_Triangle);
			if (MathUtils.Intersect(bounds.xz, bounds2.xz) && MathUtils.Intersect(triangle.xz, clearAreaData.m_Triangle.xz))
			{
				if (clearAreaData.m_OnGround && flag)
				{
					return true;
				}
				float y = bounds2.min.y;
				float num = math.max(clearAreaData.m_TopY, y + 2f);
				if (bounds.max.y >= y && bounds.min.y <= num)
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `public static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Bezier4x3 curve, System.Boolean onGround) : System.Boolean`  

```csharp
private static bool ShouldClear(NativeList<ClearAreaData> clearAreas, Triangle3 triangle, Transform ownerTransform)
	{
		Bounds3 bounds = MathUtils.Bounds(triangle);
		bool flag = math.any(math.abs(triangle.y.abc - ownerTransform.m_Position.y) <= 1f);
		for (int i = 0; i < clearAreas.Length; i++)
		{
			ClearAreaData clearAreaData = clearAreas[i];
			Bounds3 bounds2 = MathUtils.Bounds(clearAreaData.m_Triangle);
			if (MathUtils.Intersect(bounds.xz, bounds2.xz) && MathUtils.Intersect(triangle.xz, clearAreaData.m_Triangle.xz))
			{
				if (clearAreaData.m_OnGround && flag)
				{
					return true;
				}
				float y = bounds2.min.y;
				float num = math.max(clearAreaData.m_TopY, y + 2f);
				if (bounds.max.y >= y && bounds.min.y <= num)
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `public static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Game.Objects.Transform ownerTransform) : System.Boolean`  

```csharp
private static bool ShouldClear(NativeList<ClearAreaData> clearAreas, Triangle3 triangle, Transform ownerTransform)
	{
		Bounds3 bounds = MathUtils.Bounds(triangle);
		bool flag = math.any(math.abs(triangle.y.abc - ownerTransform.m_Position.y) <= 1f);
		for (int i = 0; i < clearAreas.Length; i++)
		{
			ClearAreaData clearAreaData = clearAreas[i];
			Bounds3 bounds2 = MathUtils.Bounds(clearAreaData.m_Triangle);
			if (MathUtils.Intersect(bounds.xz, bounds2.xz) && MathUtils.Intersect(triangle.xz, clearAreaData.m_Triangle.xz))
			{
				if (clearAreaData.m_OnGround && flag)
				{
					return true;
				}
				float y = bounds2.min.y;
				float num = math.max(clearAreaData.m_TopY, y + 2f);
				if (bounds.max.y >= y && bounds.min.y <= num)
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `public static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodes, Unity.Mathematics.int2 nodeRange, Game.Objects.Transform ownerTransform) : System.Boolean`  

```csharp
private static bool ShouldClear(NativeList<ClearAreaData> clearAreas, Triangle3 triangle, Transform ownerTransform)
	{
		Bounds3 bounds = MathUtils.Bounds(triangle);
		bool flag = math.any(math.abs(triangle.y.abc - ownerTransform.m_Position.y) <= 1f);
		for (int i = 0; i < clearAreas.Length; i++)
		{
			ClearAreaData clearAreaData = clearAreas[i];
			Bounds3 bounds2 = MathUtils.Bounds(clearAreaData.m_Triangle);
			if (MathUtils.Intersect(bounds.xz, bounds2.xz) && MathUtils.Intersect(triangle.xz, clearAreaData.m_Triangle.xz))
			{
				if (clearAreaData.m_OnGround && flag)
				{
					return true;
				}
				float y = bounds2.min.y;
				float num = math.max(clearAreaData.m_TopY, y + 2f);
				if (bounds.max.y >= y && bounds.min.y <= num)
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `private static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Triangle3 triangle, Game.Objects.Transform ownerTransform) : System.Boolean`  

```csharp
private static bool ShouldClear(NativeList<ClearAreaData> clearAreas, Triangle3 triangle, Transform ownerTransform)
	{
		Bounds3 bounds = MathUtils.Bounds(triangle);
		bool flag = math.any(math.abs(triangle.y.abc - ownerTransform.m_Position.y) <= 1f);
		for (int i = 0; i < clearAreas.Length; i++)
		{
			ClearAreaData clearAreaData = clearAreas[i];
			Bounds3 bounds2 = MathUtils.Bounds(clearAreaData.m_Triangle);
			if (MathUtils.Intersect(bounds.xz, bounds2.xz) && MathUtils.Intersect(triangle.xz, clearAreaData.m_Triangle.xz))
			{
				if (clearAreaData.m_OnGround && flag)
				{
					return true;
				}
				float y = bounds2.min.y;
				float num = math.max(clearAreaData.m_TopY, y + 2f);
				if (bounds.max.y >= y && bounds.min.y <= num)
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `public static TransformClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform oldTransform, Game.Objects.Transform newTransform) : System.Void`  

```csharp
public static void TransformClearAreas(NativeList<ClearAreaData> clearAreas, Transform oldTransform, Transform newTransform)
	{
		if (clearAreas.IsCreated)
		{
			Transform inverseParentTransform = ObjectUtils.InverseTransform(oldTransform);
			for (int i = 0; i < clearAreas.Length; i++)
			{
				ClearAreaData value = clearAreas[i];
				value.m_Triangle.a = ObjectUtils.LocalToWorld(newTransform, ObjectUtils.WorldToLocal(inverseParentTransform, value.m_Triangle.a));
				value.m_Triangle.b = ObjectUtils.LocalToWorld(newTransform, ObjectUtils.WorldToLocal(inverseParentTransform, value.m_Triangle.b));
				value.m_Triangle.c = ObjectUtils.LocalToWorld(newTransform, ObjectUtils.WorldToLocal(inverseParentTransform, value.m_Triangle.c));
				value.m_TopY += newTransform.m_Position.y - oldTransform.m_Position.y;
				clearAreas[i] = value;
			}
		}
	}
```


