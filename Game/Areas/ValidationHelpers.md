# Game.Areas.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise);
    private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise);
    private static Colossal.Mathematics.Line2+Segment GetEdgeLine(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise);
    private static Colossal.Mathematics.Quad2 GetEdgeQuad(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise);
    public static System.Void ValidateArea(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Area area, Game.Areas.Geometry geometry, Game.Areas.Storage storage, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateTriangle(System.Boolean editorMode, System.Boolean noErrors, System.Boolean isCounterClockwise, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Triangle triangle, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Methods

- `private static CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Boolean`  

```csharp
private static bool CheckShape(Line3.Segment line1, Line3.Segment line2, Entity entity, float minNodeDistance, NativeQueue<ErrorData>.ParallelWriter errorQueue, DynamicBuffer<Node> nodes, int index1, int index2, bool isComplete, bool isCounterClockwise)
	{
		if (MathUtils.Distance(line1.xz, line2.xz, out var t) < minNodeDistance)
		{
			Quad2 edgeQuad = GetEdgeQuad(minNodeDistance, nodes, index1, isComplete, isCounterClockwise);
			Quad2 edgeQuad2 = GetEdgeQuad(minNodeDistance, nodes, index2, isComplete, isCounterClockwise);
			if (MathUtils.Intersect(edgeQuad, line2.xz, out var t2) || MathUtils.Intersect(edgeQuad2, line1.xz, out t2))
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorSeverity = ErrorSeverity.Error,
					m_ErrorType = ErrorType.InvalidShape,
					m_TempEntity = entity,
					m_Position = math.lerp(MathUtils.Position(line1, t.x), MathUtils.Position(line2, t.y), 0.5f)
				});
				return false;
			}
		}
		return true;
	}
```

- `private static CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise) : System.Boolean`  

```csharp
private static bool CheckShape(Line3.Segment line1, Line3.Segment line2, Entity entity, float minNodeDistance, NativeQueue<ErrorData>.ParallelWriter errorQueue, DynamicBuffer<Node> nodes, int index1, int index2, bool isComplete, bool isCounterClockwise)
	{
		if (MathUtils.Distance(line1.xz, line2.xz, out var t) < minNodeDistance)
		{
			Quad2 edgeQuad = GetEdgeQuad(minNodeDistance, nodes, index1, isComplete, isCounterClockwise);
			Quad2 edgeQuad2 = GetEdgeQuad(minNodeDistance, nodes, index2, isComplete, isCounterClockwise);
			if (MathUtils.Intersect(edgeQuad, line2.xz, out var t2) || MathUtils.Intersect(edgeQuad2, line1.xz, out t2))
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorSeverity = ErrorSeverity.Error,
					m_ErrorType = ErrorType.InvalidShape,
					m_TempEntity = entity,
					m_Position = math.lerp(MathUtils.Position(line1, t.x), MathUtils.Position(line2, t.y), 0.5f)
				});
				return false;
			}
		}
		return true;
	}
```

- `private static CheckShape(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise) : System.Boolean`  

```csharp
private static bool CheckShape(Line3.Segment line1, Line3.Segment line2, Entity entity, float minNodeDistance, NativeQueue<ErrorData>.ParallelWriter errorQueue, DynamicBuffer<Node> nodes, int index1, int index2, bool isComplete, bool isCounterClockwise)
	{
		if (MathUtils.Distance(line1.xz, line2.xz, out var t) < minNodeDistance)
		{
			Quad2 edgeQuad = GetEdgeQuad(minNodeDistance, nodes, index1, isComplete, isCounterClockwise);
			Quad2 edgeQuad2 = GetEdgeQuad(minNodeDistance, nodes, index2, isComplete, isCounterClockwise);
			if (MathUtils.Intersect(edgeQuad, line2.xz, out var t2) || MathUtils.Intersect(edgeQuad2, line1.xz, out t2))
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorSeverity = ErrorSeverity.Error,
					m_ErrorType = ErrorType.InvalidShape,
					m_TempEntity = entity,
					m_Position = math.lerp(MathUtils.Position(line1, t.x), MathUtils.Position(line2, t.y), 0.5f)
				});
				return false;
			}
		}
		return true;
	}
```

- `private static GetEdgeLine(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise) : Colossal.Mathematics.Line2+Segment`  

```csharp
private static Line2.Segment GetEdgeLine(float minNodeDistance, DynamicBuffer<Node> nodes, int index, bool isComplete, bool isCounterClockwise)
	{
		Line2.Segment result = default(Line2.Segment);
		result.a = AreaUtils.GetExpandedNode(nodes, index, -0.1f, isComplete, isCounterClockwise).xz;
		result.b = AreaUtils.GetExpandedNode(nodes, index, 0f - minNodeDistance, isComplete, isCounterClockwise).xz;
		return result;
	}
```

- `private static GetEdgeQuad(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise) : Colossal.Mathematics.Quad2`  

```csharp
private static Quad2 GetEdgeQuad(float minNodeDistance, DynamicBuffer<Node> nodes, int index, bool isComplete, bool isCounterClockwise)
	{
		int index2 = math.select(index - 1, index + nodes.Length - 1, index == 0);
		Quad2 result = default(Quad2);
		result.a = AreaUtils.GetExpandedNode(nodes, index2, 0f - minNodeDistance, isComplete, isCounterClockwise).xz;
		result.b = AreaUtils.GetExpandedNode(nodes, index2, -0.1f, isComplete, isCounterClockwise).xz;
		result.c = AreaUtils.GetExpandedNode(nodes, index, -0.1f, isComplete, isCounterClockwise).xz;
		result.d = AreaUtils.GetExpandedNode(nodes, index, 0f - minNodeDistance, isComplete, isCounterClockwise).xz;
		return result;
	}
```

- `public static ValidateArea(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Area area, Game.Areas.Geometry geometry, Game.Areas.Storage storage, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateArea(bool editorMode, Entity entity, Temp temp, Owner owner, Area area, Geometry geometry, Storage storage, DynamicBuffer<Node> nodes, PrefabRef prefabRef, ValidationSystem.EntityData data, NativeQuadTree<Entity, QuadTreeBoundsXZ> objectSearchTree, NativeQuadTree<Entity, QuadTreeBoundsXZ> netSearchTree, NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ> areaSearchTree, WaterSurfaceData waterSurfaceData, TerrainHeightData terrainHeightData, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		if ((area.m_Flags & AreaFlags.Slave) != 0)
		{
			return;
		}
		float minNodeDistance = AreaUtils.GetMinNodeDistance(data.m_PrefabAreaGeometry[prefabRef.m_Prefab]);
		bool flag = true;
		bool flag2 = (area.m_Flags & AreaFlags.Complete) != 0;
		bool isCounterClockwise = (area.m_Flags & AreaFlags.CounterClockwise) != 0;
		if (nodes.Length == 2)
		{
			ValidateTriangle(editorMode, noErrors: false, isCounterClockwise, entity, temp, owner, new Triangle(0, 1, 1), data, objectSearchTree, netSearchTree, areaSearchTree, waterSurfaceData, terrainHeightData, errorQueue);
		}
		else if (nodes.Length == 3)
		{
			if ((temp.m_Flags & TempFlags.Delete) == 0)
			{
				Line3.Segment line = new Line3.Segment(nodes[0].m_Position, nodes[1].m_Position);
				Line3.Segment line2 = new Line3.Segment(nodes[1].m_Position, nodes[2].m_Position);
				flag &= CheckShape(line, nodes[2].m_Position, entity, minNodeDistance, errorQueue);
				flag &= CheckShape(line2, nodes[0].m_Position, entity, minNodeDistance, errorQueue);
				if (flag2)
				{
					Line3.Segment line3 = new Line3.Segment(nodes[2].m_Position, nodes[0].m_Position);
					flag &= CheckShape(line3, nodes[1].m_Position, entity, minNodeDistance, errorQueue);
				}
			}
		}
		else if (nodes.Length > 3 && (temp.m_Flags & TempFlags.Delete) == 0)
		{
			int num = 0;
			int num2 = math.select(nodes.Length - 1, nodes.Length, flag2);
			NativeArray<Bounds2> nativeArray = default(NativeArray<Bounds2>);
			int num3 = num2 - num - 2;
			int num4 = 0;
			float2 t;
			if (num3 > 10)
			{
				int num5 = -1;
				int num6 = 0;
				while (num3 >= 2)
				{
					num5 += 1 << num6++;
					num3 >>= 1;
				}
				nativeArray = new NativeArray<Bounds2>(num5, Allocator.Temp);
				num4 = --num6;
				int num7 = 1 << num6;
				int num8 = num5 - num7;
				num3 = num2 - num - 2;
				Bounds2 bounds = default(Bounds2);
				for (int i = 0; i < num7; i++)
				{
					int num9 = i * num3 >> num6;
					int num10 = (i + 1) * num3 >> num6;
					t = (bounds.min = (bounds.max = nodes[num9++].m_Position.xz));
					for (int j = num9; j <= num10; j++)
					{
						bounds |= nodes[j].m_Position.xz;
					}
					nativeArray[num8 + i] = MathUtils.Expand(bounds, minNodeDistance);
				}
				while (--num6 > 0)
				{
					int num11 = num8;
					num7 = 1 << num6;
					num8 -= num7;
					for (int k = 0; k < num7; k++)
					{
						nativeArray[num8 + k] = nativeArray[num11 + (k << 1)] | nativeArray[num11 + (k << 1) + 1];
					}
				}
			}
			Line3.Segment line4 = new Line3.Segment
			{
				a = nodes[num++].m_Position
			};
			for (int l = num; l <= num2; l++)
			{
				int num12 = math.select(l, 0, l == nodes.Length);
				line4.b = nodes[num12].m_Position;
				int num13 = math.select(0, 1, l == nodes.Length);
				int num14 = l - 2;
				if (nativeArray.IsCreated)
				{
					int num15 = 0;
					int num16 = 1;
					int num17 = 0;
					while (num16 > 0)
					{
						if (MathUtils.Intersect(nativeArray[num15 + num17], line4.xz, out t))
						{
							if (num16 != num4)
							{
								num17 <<= 1;
								num15 += 1 << num16++;
								continue;
							}
							int num18 = math.max(num13, num17 * num3 >> num16);
							int num19 = math.min(num14, (num17 + 1) * num3 >> num16);
							if (num19 > num18)
							{
								Line3.Segment line5 = new Line3.Segment
								{
									a = nodes[num18++].m_Position
								};
								for (int m = num18; m <= num19; m++)
								{
									line5.b = nodes[m].m_Position;
									flag &= CheckShape(line4, line5, entity, minNodeDistance, errorQueue, nodes, num12, m, flag2, isCounterClockwise);
									line5.a = line5.b;
								}
							}
						}
						while ((num17 & 1) != 0)
						{
							num17 >>= 1;
							num15 -= 1 << --num16;
						}
						num17++;
					}
				}
				else
				{
					Line3.Segment line6 = new Line3.Segment
					{
						a = nodes[num13++].m_Position
					};
					for (int n = num13; n <= num14; n++)
					{
						line6.b = nodes[n].m_Position;
						flag &= CheckShape(line4, line6, entity, minNodeDistance, errorQueue, nodes, num12, n, flag2, isCounterClockwise);
						line6.a = line6.b;
					}
				}
				if (l > num || flag2)
				{
					int num20 = l - 2;
					num20 += math.select(0, nodes.Length, num20 < 0);
					flag &= CheckShape(line4, nodes[num20].m_Position, entity, minNodeDistance, errorQueue);
				}
				if (l < num2 || flag2)
				{
					int num21 = l + 1;
					num21 -= math.select(0, nodes.Length, num21 >= nodes.Length);
					flag &= CheckShape(line4, nodes[num21].m_Position, entity, minNodeDistance, errorQueue);
				}
				if (!flag2)
				{
					if (l > num)
					{
						flag &= CheckShape(line4, nodes[0].m_Position, entity, minNodeDistance, errorQueue, nodes, num12, 0, flag2, isCounterClockwise);
					}
					if (l < num2)
					{
						flag &= CheckShape(line4, nodes[nodes.Length - 1].m_Position, entity, minNodeDistance, errorQueue, nodes, num12, nodes.Length - 1, flag2, isCounterClockwise);
					}
				}
				line4.a = line4.b;
			}
			if (nativeArray.IsCreated)
			{
				nativeArray.Dispose();
			}
		}
		if (!flag2 && nodes.Length >= 3)
		{
			ValidateTriangle(editorMode, noErrors: false, isCounterClockwise, entity, temp, owner, new Triangle(nodes.Length - 2, nodes.Length - 1, nodes.Length - 1), data, objectSearchTree, netSearchTree, areaSearchTree, waterSurfaceData, terrainHeightData, errorQueue);
		}
		if (flag && flag2 && (area.m_Flags & AreaFlags.NoTriangles) != 0 && nodes.Length >= 3)
		{
			float3 position = 0;
			for (int num22 = 0; num22 < nodes.Length; num22++)
			{
				position += nodes[num22].m_Position;
			}
			position /= (float)nodes.Length;
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorSeverity = ErrorSeverity.Error,
				m_ErrorType = ErrorType.InvalidShape,
				m_TempEntity = entity,
				m_Position = position
			});
			flag = false;
		}
		if ((temp.m_Flags & TempFlags.Delete) == 0 && data.m_Transform.HasComponent(owner.m_Owner) && data.m_PrefabLotData.HasComponent(prefabRef.m_Prefab))
		{
			float2 xz = data.m_Transform[owner.m_Owner].m_Position.xz;
			float maxRadius = data.m_PrefabLotData[prefabRef.m_Prefab].m_MaxRadius;
			if (maxRadius > 0f)
			{
				for (int num23 = 0; num23 < nodes.Length; num23++)
				{
					if (math.distance(xz, nodes[num23].m_Position.xz) > maxRadius)
					{
						errorQueue.Enqueue(new ErrorData
						{
							m_ErrorSeverity = ErrorSeverity.Error,
							m_ErrorType = ErrorType.LongDistance,
							m_TempEntity = entity,
							m_PermanentEntity = owner.m_Owner,
							m_Position = nodes[num23].m_Position
						});
					}
				}
			}
		}
		if ((temp.m_Flags & TempFlags.Delete) == 0 && flag && flag2 && data.m_PrefabStorageArea.HasComponent(prefabRef.m_Prefab))
		{
			StorageAreaData prefabStorageData = data.m_PrefabStorageArea[prefabRef.m_Prefab];
			int num24 = AreaUtils.CalculateStorageCapacity(geometry, prefabStorageData);
			if (storage.m_Amount > num24)
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorSeverity = ErrorSeverity.Error,
					m_ErrorType = ErrorType.SmallArea,
					m_TempEntity = entity,
					m_Position = geometry.m_CenterPosition
				});
			}
		}
	}
```

- `public static ValidateTriangle(System.Boolean editorMode, System.Boolean noErrors, System.Boolean isCounterClockwise, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Triangle triangle, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateTriangle(bool editorMode, bool noErrors, bool isCounterClockwise, Entity entity, Temp temp, Owner owner, Triangle triangle, ValidationSystem.EntityData data, NativeQuadTree<Entity, QuadTreeBoundsXZ> objectSearchTree, NativeQuadTree<Entity, QuadTreeBoundsXZ> netSearchTree, NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ> areaSearchTree, WaterSurfaceData waterSurfaceData, TerrainHeightData terrainHeightData, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		DynamicBuffer<Node> nodes = data.m_AreaNodes[entity];
		PrefabRef prefabRef = data.m_PrefabRef[entity];
		AreaGeometryData areaGeometryData = data.m_PrefabAreaGeometry[prefabRef.m_Prefab];
		Triangle3 triangle2 = AreaUtils.GetTriangle3(nodes, triangle);
		Bounds3 bounds = AreaUtils.GetBounds(triangle, triangle2, areaGeometryData);
		Bounds1 heightRange = triangle.m_HeightRange;
		heightRange.max += areaGeometryData.m_MaxHeight;
		Entity entity2 = entity;
		if (owner.m_Owner != Entity.Null && !data.m_AssetStamp.HasComponent(owner.m_Owner))
		{
			entity2 = owner.m_Owner;
			while (data.m_Owner.HasComponent(entity2) && !data.m_Building.HasComponent(entity2))
			{
				Entity owner2 = data.m_Owner[entity2].m_Owner;
				if (data.m_AssetStamp.HasComponent(owner2))
				{
					break;
				}
				entity2 = owner2;
			}
		}
		Entity entity3 = Entity.Null;
		Entity ignoreEntity = Entity.Null;
		ErrorSeverity errorSeverity = ErrorSeverity.Error;
		if (noErrors)
		{
			entity3 = entity2;
			while (data.m_Owner.HasComponent(entity3))
			{
				entity3 = data.m_Owner[entity3].m_Owner;
			}
			if (data.m_Attachment.TryGetComponent(entity3, out var componentData))
			{
				ignoreEntity = componentData.m_Attached;
			}
			errorSeverity = ErrorSeverity.Warning;
		}
		AreaUtils.SetCollisionFlags(ref areaGeometryData, !editorMode || owner.m_Owner != Entity.Null);
		if ((areaGeometryData.m_Flags & GeometryFlags.PhysicalGeometry) != 0)
		{
			CollisionMask collisionMask = AreaUtils.GetCollisionMask(areaGeometryData);
			if ((temp.m_Flags & TempFlags.Delete) == 0)
			{
				ObjectIterator iterator = new ObjectIterator
				{
					m_AreaEntity = entity,
					m_OriginalAreaEntity = temp.m_Original,
					m_IgnoreEntity = entity3,
					m_IgnoreEntity2 = ignoreEntity,
					m_TriangleBounds = bounds,
					m_HeightRange = heightRange,
					m_Triangle = triangle2,
					m_ErrorSeverity = errorSeverity,
					m_CollisionMask = collisionMask,
					m_PrefabAreaData = areaGeometryData,
					m_Data = data,
					m_ErrorQueue = errorQueue,
					m_EditorMode = editorMode
				};
				objectSearchTree.Iterate(ref iterator);
			}
			if ((temp.m_Flags & TempFlags.Delete) == 0)
			{
				NetIterator iterator2 = new NetIterator
				{
					m_AreaEntity = entity,
					m_OriginalAreaEntity = temp.m_Original,
					m_IgnoreEntity = entity3,
					m_IgnoreEntity2 = ignoreEntity,
					m_TriangleBounds = bounds,
					m_HeightRange = heightRange,
					m_Triangle = triangle2,
					m_ErrorSeverity = errorSeverity,
					m_CollisionMask = collisionMask,
					m_Data = data,
					m_ErrorQueue = errorQueue,
					m_EditorMode = editorMode
				};
				netSearchTree.Iterate(ref iterator2);
			}
		}
		if ((areaGeometryData.m_Flags & (GeometryFlags.PhysicalGeometry | GeometryFlags.ProtectedArea)) != 0 || entity2 == entity || (!editorMode && ((temp.m_Flags & (TempFlags.Delete | TempFlags.Essential)) == TempFlags.Essential || (temp.m_Flags & TempFlags.Create) != 0)))
		{
			AreaIterator iterator3 = new AreaIterator
			{
				m_AreaEntity = entity,
				m_IgnoreEntity = entity3,
				m_IgnoreEntity2 = ignoreEntity,
				m_TopLevelEntity = entity2,
				m_TriangleBounds = bounds,
				m_IgnoreCollisions = ((temp.m_Flags & TempFlags.Delete) != 0),
				m_EditorMode = editorMode,
				m_Essential = ((temp.m_Flags & TempFlags.Essential) != 0),
				m_PrefabAreaData = areaGeometryData,
				m_ErrorSeverity = errorSeverity,
				m_Data = data,
				m_ErrorQueue = errorQueue
			};
			if (triangle.m_Indices.y == triangle.m_Indices.z)
			{
				iterator3.m_Triangle = AreaUtils.GetTriangle2(nodes, triangle);
			}
			else
			{
				iterator3.m_Triangle = AreaUtils.GetTriangle2(nodes, triangle, -0.1f, isCounterClockwise);
			}
			areaSearchTree.Iterate(ref iterator3);
		}
		if ((areaGeometryData.m_Flags & GeometryFlags.PhysicalGeometry) == 0 || (areaGeometryData.m_Flags & (GeometryFlags.OnWaterSurface | GeometryFlags.RequireWater)) == GeometryFlags.OnWaterSurface)
		{
			return;
		}
		float sampleInterval = WaterUtils.GetSampleInterval(ref waterSurfaceData);
		int2 @int = (int2)math.ceil(new float2(math.distance(triangle2.a.xz, triangle2.b.xz), math.distance(triangle2.a.xz, triangle2.c.xz)) / sampleInterval);
		float num = 1f / (float)math.max(1, @int.x);
		float num2 = areaGeometryData.m_SnapDistance * 0.01f;
		Bounds3 bounds2 = default(Bounds3);
		bounds2.min = float.MaxValue;
		bounds2.max = float.MinValue;
		bool flag = false;
		bool flag2 = false;
		OriginalAreaIterator iterator4 = default(OriginalAreaIterator);
		if (data.m_AreaNodes.TryGetBuffer(temp.m_Original, out var bufferData))
		{
			iterator4 = new OriginalAreaIterator
			{
				m_AreaEntity = temp.m_Original,
				m_Offset = num2,
				m_Nodes = bufferData,
				m_Triangles = data.m_AreaTriangles[temp.m_Original]
			};
		}
		for (int i = 0; i <= @int.x; i++)
		{
			float2 t = new float2
			{
				x = (float)i * num
			};
			int num3 = ((@int.x - i) * @int.y + (@int.x >> 1)) / math.max(1, @int.x);
			float num4 = (1f - t.x) / (float)math.max(1, num3);
			if ((areaGeometryData.m_Flags & GeometryFlags.RequireWater) != 0)
			{
				for (int j = 0; j <= num3; j++)
				{
					t.y = (float)j * num4;
					float3 @float = MathUtils.Position(triangle2, t);
					if (!(WaterUtils.SampleDepth(ref waterSurfaceData, @float) < 0.2f))
					{
						continue;
					}
					if (iterator4.m_Nodes.IsCreated)
					{
						iterator4.m_Bounds = new Bounds2(@float.xz - num2, @float.xz + num2);
						iterator4.m_Position = @float.xz;
						iterator4.m_Result = false;
						areaSearchTree.Iterate(ref iterator4);
						if (iterator4.m_Result)
						{
							continue;
						}
					}
					bounds2 |= @float;
					flag2 = true;
				}
				continue;
			}
			for (int k = 0; k <= num3; k++)
			{
				t.y = (float)k * num4;
				float3 float2 = MathUtils.Position(triangle2, t);
				if (!(WaterUtils.SampleDepth(ref waterSurfaceData, float2) >= 0.2f))
				{
					continue;
				}
				if (iterator4.m_Nodes.IsCreated)
				{
					iterator4.m_Bounds = new Bounds2(float2.xz - num2, float2.xz + num2);
					iterator4.m_Position = float2.xz;
					iterator4.m_Result = false;
					areaSearchTree.Iterate(ref iterator4);
					if (iterator4.m_Result)
					{
						continue;
					}
				}
				bounds2 |= float2;
				flag = true;
			}
		}
		if (flag)
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorType = ErrorType.InWater,
				m_ErrorSeverity = ErrorSeverity.Error,
				m_TempEntity = entity,
				m_Position = MathUtils.Center(bounds2)
			});
		}
		if (flag2)
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorType = ErrorType.NoWater,
				m_ErrorSeverity = ErrorSeverity.Error,
				m_TempEntity = entity,
				m_Position = MathUtils.Center(bounds2)
			});
		}
	}
```


## Nested types

- `Game.Areas.ValidationHelpers+OriginalAreaIterator`  
- `Game.Areas.ValidationHelpers+ObjectIterator`  
- `Game.Areas.ValidationHelpers+NetIterator`  
- `Game.Areas.ValidationHelpers+AreaIterator`  
- `Game.Areas.ValidationHelpers+BrushAreaIterator`  

