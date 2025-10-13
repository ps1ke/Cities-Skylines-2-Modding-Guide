# Game.Areas.AreaUtils

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AreaUtils
{
    public static const System.Single NODE_DISTANCE_TOLERANCE;

    public static Game.Areas.Node AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData);
    public static Game.Areas.Node AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData);
    public static System.Void ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Areas.DistrictModifierType type);
    public static System.Single CalculateExtractorObjectArea(Game.Areas.Geometry geometry, Game.Areas.Extractor extractor, Game.Prefabs.ExtractorAreaData extractorAreaData);
    public static Unity.Mathematics.float4x4 CalculateLabelMatrix(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition, Unity.Mathematics.quaternion labelRotation);
    public static Unity.Mathematics.float3 CalculateLabelPosition(Game.Areas.Geometry geometry);
    public static Unity.Mathematics.quaternion CalculateLabelRotation(Unity.Mathematics.float3 cameraRight);
    public static System.Single CalculateLabelScale(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition);
    public static System.Int32 CalculateStorageCapacity(Game.Areas.Geometry geometry, Game.Prefabs.StorageAreaData prefabStorageData);
    public static System.Single CalculateStorageObjectArea(Game.Areas.Geometry geometry, Game.Areas.Storage storage, Game.Prefabs.StorageAreaData prefabStorageData);
    public static System.Boolean CheckOption(Game.Areas.District district, Game.Areas.DistrictOption option);
    public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity district, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts);
    public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity district1, Unity.Entities.Entity district2, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts);
    public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity building, Unity.Entities.DynamicBuffer<Game.Areas.ServiceDistrict> serviceDistricts, Unity.Entities.ComponentLookup`1[[Game.Areas.CurrentDistrict, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentDistricts);
    public static System.Void FindAreaPath(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.Entity startEntity, System.Single startCurvePos, Unity.Entities.Entity endEntity, System.Single endCurvePos, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData);
    public static Colossal.Mathematics.Bounds3 GetBounds(Game.Areas.Triangle triangle, Colossal.Mathematics.Triangle3 triangle3, Game.Prefabs.AreaGeometryData areaData);
    public static Game.Common.CollisionMask GetCollisionMask(Game.Prefabs.AreaGeometryData areaGeometryData);
    public static Unity.Mathematics.float3 GetElevations(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
    public static Unity.Mathematics.float3 GetExpandedNode(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise);
    public static Unity.Mathematics.float3 GetExpandedNode(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise);
    public static Unity.Mathematics.float3 GetExpandedNode<TNodeList>(TNodeList nodes, System.Int32 index, System.Int32 prevIndex, System.Int32 nextIndex, System.Single expandAmount, System.Boolean isCounterClockwise);
    public static System.Single GetMinNodeDistance(Game.Prefabs.AreaGeometryData areaData);
    public static System.Single GetMinNodeDistance(Game.Areas.AreaType areaType);
    public static Unity.Mathematics.float3 GetRandomPosition(Unity.Mathematics.Random& random, Game.Areas.Geometry geometry, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles);
    public static Unity.Mathematics.quaternion GetRandomRotation(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
    public static Colossal.Mathematics.Triangle2 GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
    public static Colossal.Mathematics.Triangle2 GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle, System.Single expandAmount, System.Boolean isCounterClockwise);
    public static Colossal.Mathematics.Triangle3 GetTriangle3(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
    public static Game.Areas.AreaTypeMask GetTypeMask(Game.Areas.AreaType type);
    public static System.Boolean HasOption(Game.Prefabs.DistrictOptionData optionData, Game.Areas.DistrictOption option);
    public static System.Boolean IntersectArea(Unity.Mathematics.float3 position, System.Single radius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles);
    public static System.Boolean IntersectEdges(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
    public static System.Boolean IntersectObjects(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride);
    public static Unity.Mathematics.bool3 IsEdge(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
    public static System.Boolean SelectAreaPrefab(Unity.Entities.DynamicBuffer<Game.Prefabs.PlaceholderObjectElement> placeholderElements, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> spawnableDatas, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> selectedSpawnables, Unity.Mathematics.Random& random, Unity.Entities.Entity& result, System.Int32& seed);
    public static System.Void SetCollisionFlags(Game.Prefabs.AreaGeometryData& areaGeometryData, System.Boolean ignoreMarkers);
    public static System.Boolean TryFitInside(Unity.Mathematics.float3& position, System.Single radius, System.Single extraRadius, Game.Areas.Area area, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride);
    public static System.Boolean TryGetRandomObjectLocation(Unity.Mathematics.Random& random, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Areas.Area area, Game.Areas.Geometry geometry, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, Game.Objects.Transform& transform);
}
```


## Fields

- `public static const System.Single NODE_DISTANCE_TOLERANCE`  

```csharp
public static const System.Single NODE_DISTANCE_TOLERANCE;
```


## Methods

- `public static AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData) : Game.Areas.Node`  

```csharp
public static Node AdjustPosition(Node node, ref TerrainHeightData terrainHeightData)
	{
		Node result = node;
		result.m_Position.y = TerrainUtils.SampleHeight(ref terrainHeightData, node.m_Position);
		return result;
	}
```

- `public static AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Areas.Node`  

```csharp
public static Node AdjustPosition(Node node, ref TerrainHeightData terrainHeightData)
	{
		Node result = node;
		result.m_Position.y = TerrainUtils.SampleHeight(ref terrainHeightData, node.m_Position);
		return result;
	}
```

- `public static ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Areas.DistrictModifierType type) : System.Void`  

```csharp
public static void ApplyModifier(ref float value, DynamicBuffer<DistrictModifier> modifiers, DistrictModifierType type)
	{
		if (modifiers.Length > (int)type)
		{
			float2 delta = modifiers[(int)type].m_Delta;
			value += delta.x;
			value += value * delta.y;
		}
	}
```

- `public static CalculateExtractorObjectArea(Game.Areas.Geometry geometry, Game.Areas.Extractor extractor, Game.Prefabs.ExtractorAreaData extractorAreaData) : System.Single`  

```csharp
public static float CalculateExtractorObjectArea(Geometry geometry, Extractor extractor, ExtractorAreaData extractorAreaData)
	{
		return math.min(extractor.m_TotalExtracted * extractorAreaData.m_ObjectSpawnFactor, geometry.m_SurfaceArea * extractorAreaData.m_MaxObjectArea);
	}
```

- `public static CalculateLabelMatrix(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition, Unity.Mathematics.quaternion labelRotation) : Unity.Mathematics.float4x4`  

```csharp
public static float4x4 CalculateLabelMatrix(float3 cameraPosition, float3 labelPosition, quaternion labelRotation)
	{
		float num = CalculateLabelScale(cameraPosition, labelPosition);
		return float4x4.TRS(labelPosition, labelRotation, num);
	}
```

- `public static CalculateLabelPosition(Game.Areas.Geometry geometry) : Unity.Mathematics.float3`  

```csharp
public static float3 CalculateLabelPosition(Geometry geometry)
	{
		return geometry.m_CenterPosition;
	}
```

- `public static CalculateLabelRotation(Unity.Mathematics.float3 cameraRight) : Unity.Mathematics.quaternion`  

```csharp
public static quaternion CalculateLabelRotation(float3 cameraRight)
	{
		float3 up = math.cross(cameraRight, math.up());
		return quaternion.LookRotation(new float3(0f, -1f, 0f), up);
	}
```

- `public static CalculateLabelScale(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition) : System.Single`  

```csharp
public static float CalculateLabelScale(float3 cameraPosition, float3 labelPosition)
	{
		return math.max(0.01f, math.sqrt(math.distance(cameraPosition, labelPosition) * 0.001f));
	}
```

- `public static CalculateStorageCapacity(Game.Areas.Geometry geometry, Game.Prefabs.StorageAreaData prefabStorageData) : System.Int32`  

```csharp
public static int CalculateStorageCapacity(Geometry geometry, StorageAreaData prefabStorageData)
	{
		return Mathf.RoundToInt(geometry.m_SurfaceArea * (1f / 64f) * (float)prefabStorageData.m_Capacity);
	}
```

- `public static CalculateStorageObjectArea(Game.Areas.Geometry geometry, Game.Areas.Storage storage, Game.Prefabs.StorageAreaData prefabStorageData) : System.Single`  

```csharp
public static float CalculateStorageObjectArea(Geometry geometry, Storage storage, StorageAreaData prefabStorageData)
	{
		float y = geometry.m_SurfaceArea * (1f / 64f) * (float)prefabStorageData.m_Capacity;
		float x = (float)storage.m_Amount / math.max(1f, y);
		return math.min(0.25f, math.sqrt(x)) * geometry.m_SurfaceArea;
	}
```

- `public static CheckOption(Game.Areas.District district, Game.Areas.DistrictOption option) : System.Boolean`  

```csharp
public static bool CheckOption(District district, DistrictOption option)
	{
		return (district.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```

- `public static CheckServiceDistrict(Unity.Entities.Entity district, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts) : System.Boolean`  

```csharp
public static bool CheckServiceDistrict(Entity building, DynamicBuffer<ServiceDistrict> serviceDistricts, ref ComponentLookup<CurrentDistrict> currentDistricts)
	{
		if (serviceDistricts.IsCreated && serviceDistricts.Length != 0 && currentDistricts.TryGetComponent(building, out var componentData))
		{
			return CollectionUtils.ContainsValue(serviceDistricts, new ServiceDistrict(componentData.m_District));
		}
		return true;
	}
```

- `public static CheckServiceDistrict(Unity.Entities.Entity district1, Unity.Entities.Entity district2, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts) : System.Boolean`  

```csharp
public static bool CheckServiceDistrict(Entity building, DynamicBuffer<ServiceDistrict> serviceDistricts, ref ComponentLookup<CurrentDistrict> currentDistricts)
	{
		if (serviceDistricts.IsCreated && serviceDistricts.Length != 0 && currentDistricts.TryGetComponent(building, out var componentData))
		{
			return CollectionUtils.ContainsValue(serviceDistricts, new ServiceDistrict(componentData.m_District));
		}
		return true;
	}
```

- `public static CheckServiceDistrict(Unity.Entities.Entity building, Unity.Entities.DynamicBuffer<Game.Areas.ServiceDistrict> serviceDistricts, Unity.Entities.ComponentLookup`1[[Game.Areas.CurrentDistrict, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentDistricts) : System.Boolean`  

```csharp
public static bool CheckServiceDistrict(Entity building, DynamicBuffer<ServiceDistrict> serviceDistricts, ref ComponentLookup<CurrentDistrict> currentDistricts)
	{
		if (serviceDistricts.IsCreated && serviceDistricts.Length != 0 && currentDistricts.TryGetComponent(building, out var componentData))
		{
			return CollectionUtils.ContainsValue(serviceDistricts, new ServiceDistrict(componentData.m_District));
		}
		return true;
	}
```

- `public static FindAreaPath(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.Entity startEntity, System.Single startCurvePos, Unity.Entities.Entity endEntity, System.Single endCurvePos, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData) : System.Void`  

```csharp
public static void FindAreaPath(ref Unity.Mathematics.Random random, NativeList<PathElement> path, DynamicBuffer<Game.Net.SubLane> lanes, Entity startEntity, float startCurvePos, Entity endEntity, float endCurvePos, ComponentLookup<Lane> laneData, ComponentLookup<Curve> curveData)
	{
		if (startEntity == endEntity)
		{
			path.Add(new PathElement(startEntity, new float2(startCurvePos, endCurvePos)));
			return;
		}
		NativeParallelMultiHashMap<PathNode, Entity> nativeParallelMultiHashMap = new NativeParallelMultiHashMap<PathNode, Entity>(lanes.Length * 2, Allocator.Temp);
		NativeParallelHashMap<PathNode, PathElement> nativeParallelHashMap = new NativeParallelHashMap<PathNode, PathElement>(lanes.Length + 1, Allocator.Temp);
		NativeMinHeap<FixPathItem> nativeMinHeap = new NativeMinHeap<FixPathItem>(lanes.Length, Allocator.Temp);
		for (int i = 0; i < lanes.Length; i++)
		{
			Entity subLane = lanes[i].m_SubLane;
			Lane lane = laneData[subLane];
			nativeParallelMultiHashMap.Add(lane.m_StartNode, subLane);
			nativeParallelMultiHashMap.Add(lane.m_EndNode, subLane);
		}
		Lane lane2 = laneData[endEntity];
		Curve curve = curveData[endEntity];
		float cost = random.NextFloat(0.5f, 1f) * curve.m_Length * endCurvePos;
		float cost2 = random.NextFloat(0.5f, 1f) * curve.m_Length * (1f - endCurvePos);
		nativeMinHeap.Insert(new FixPathItem(lane2.m_StartNode, new PathElement(endEntity, new float2(0f, endCurvePos)), cost));
		nativeMinHeap.Insert(new FixPathItem(lane2.m_EndNode, new PathElement(endEntity, new float2(1f, endCurvePos)), cost2));
		while (nativeMinHeap.Length != 0)
		{
			FixPathItem fixPathItem = nativeMinHeap.Extract();
			if (!nativeParallelHashMap.TryAdd(fixPathItem.m_Node, fixPathItem.m_PathElement))
			{
				continue;
			}
			if (fixPathItem.m_PathElement.m_Target == startEntity)
			{
				path.Add(in fixPathItem.m_PathElement);
				Lane lane3 = laneData[startEntity];
				PathNode key = ((fixPathItem.m_PathElement.m_TargetDelta.y == 0f) ? lane3.m_StartNode : lane3.m_EndNode);
				PathElement item;
				while (nativeParallelHashMap.TryGetValue(key, out item))
				{
					path.Add(in item);
					if (item.m_Target == endEntity)
					{
						break;
					}
					lane3 = laneData[item.m_Target];
					key = ((item.m_TargetDelta.y == 0f) ? lane3.m_StartNode : lane3.m_EndNode);
				}
				break;
			}
			if (!nativeParallelMultiHashMap.TryGetFirstValue(fixPathItem.m_Node, out var item2, out var it))
			{
				continue;
			}
			do
			{
				if (item2 == fixPathItem.m_PathElement.m_Target)
				{
					continue;
				}
				Lane lane4 = laneData[item2];
				Curve curve2 = curveData[item2];
				if (lane4.m_EndNode.Equals(fixPathItem.m_Node))
				{
					if (item2 == startEntity)
					{
						float num = random.NextFloat(0.5f, 1f) * curve2.m_Length * (1f - startCurvePos);
						nativeMinHeap.Insert(new FixPathItem(lane4.m_MiddleNode, new PathElement(startEntity, new float2(startCurvePos, 1f)), fixPathItem.m_Cost + num));
					}
					else if (!nativeParallelHashMap.ContainsKey(lane4.m_StartNode))
					{
						float num2 = random.NextFloat(0.5f, 1f) * curve2.m_Length;
						nativeMinHeap.Insert(new FixPathItem(lane4.m_StartNode, new PathElement(item2, new float2(0f, 1f)), fixPathItem.m_Cost + num2));
					}
				}
				else if (lane4.m_StartNode.Equals(fixPathItem.m_Node))
				{
					if (item2 == startEntity)
					{
						float num3 = random.NextFloat(0.5f, 1f) * curve2.m_Length * startCurvePos;
						nativeMinHeap.Insert(new FixPathItem(lane4.m_MiddleNode, new PathElement(startEntity, new float2(startCurvePos, 0f)), fixPathItem.m_Cost + num3));
					}
					else if (!nativeParallelHashMap.ContainsKey(lane4.m_EndNode))
					{
						float num4 = random.NextFloat(0.5f, 1f) * curve2.m_Length;
						nativeMinHeap.Insert(new FixPathItem(lane4.m_EndNode, new PathElement(item2, new float2(1f, 0f)), fixPathItem.m_Cost + num4));
					}
				}
			}
			while (nativeParallelMultiHashMap.TryGetNextValue(out item2, ref it));
		}
		nativeParallelMultiHashMap.Dispose();
		nativeParallelHashMap.Dispose();
		nativeMinHeap.Dispose();
	}
```

- `public static GetBounds(Game.Areas.Triangle triangle, Colossal.Mathematics.Triangle3 triangle3, Game.Prefabs.AreaGeometryData areaData) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 GetBounds(Triangle triangle, Triangle3 triangle3, AreaGeometryData areaData)
	{
		Bounds3 result = MathUtils.Bounds(triangle3);
		result.min.y += triangle.m_HeightRange.min;
		result.max.y += triangle.m_HeightRange.max + areaData.m_MaxHeight;
		return result;
	}
```

- `public static GetCollisionMask(Game.Prefabs.AreaGeometryData areaGeometryData) : Game.Common.CollisionMask`  

```csharp
public static CollisionMask GetCollisionMask(AreaGeometryData areaGeometryData)
	{
		CollisionMask collisionMask = CollisionMask.OnGround | CollisionMask.Overground | CollisionMask.ExclusiveGround;
		if (areaGeometryData.m_Type != AreaType.Lot)
		{
			collisionMask |= CollisionMask.Underground;
		}
		return collisionMask;
	}
```

- `public static GetElevations(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Unity.Mathematics.float3`  

```csharp
public static float3 GetElevations(DynamicBuffer<Node> nodes, Triangle triangle)
	{
		return new float3(nodes[triangle.m_Indices.x].m_Elevation, nodes[triangle.m_Indices.y].m_Elevation, nodes[triangle.m_Indices.z].m_Elevation);
	}
```

- `public static GetExpandedNode(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  

```csharp
public static float3 GetExpandedNode(NativeArray<SubAreaNode> nodes, int index, float expandAmount, bool isComplete, bool isCounterClockwise)
	{
		if (!isComplete)
		{
			if (nodes.Length == 1)
			{
				return nodes[index].m_Position;
			}
			if (index == 0)
			{
				float2 xz = nodes[math.select(index + 1, 0, index == nodes.Length - 1)].m_Position.xz;
				float3 position = nodes[index].m_Position;
				float2 @float = math.normalizesafe(xz - position.xz);
				float2 float2 = math.select(MathUtils.Left(@float), MathUtils.Right(@float), isCounterClockwise) - @float;
				position.xz += float2 * expandAmount;
				return position;
			}
			if (index == nodes.Length - 1)
			{
				float2 xz2 = nodes[math.select(index - 1, nodes.Length - 1, index == 0)].m_Position.xz;
				float3 position2 = nodes[index].m_Position;
				float2 float3 = math.normalizesafe(xz2 - position2.xz);
				float2 float4 = math.select(MathUtils.Right(float3), MathUtils.Left(float3), isCounterClockwise) - float3;
				position2.xz += float4 * expandAmount;
				return position2;
			}
		}
		float2 xz3 = nodes[math.select(index - 1, nodes.Length - 1, index == 0)].m_Position.xz;
		float2 xz4 = nodes[math.select(index + 1, 0, index == nodes.Length - 1)].m_Position.xz;
		float3 position3 = nodes[index].m_Position;
		float2 float5 = math.normalizesafe(xz3 - position3.xz);
		float2 y = math.normalizesafe(xz4 - position3.xz);
		float2 float6 = math.select(MathUtils.Right(float5), MathUtils.Left(float5), isCounterClockwise);
		float num = math.acos(math.clamp(math.dot(float5, y), -1f, 1f));
		float num2 = math.sign(math.dot(float6, y));
		float num3 = math.tan(num * 0.5f);
		float6 += float5 * math.select(num2 / num3, 0f, num3 < 0.001f);
		position3.xz += float6 * expandAmount;
		return position3;
	}
```

- `public static GetExpandedNode(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  

```csharp
public static float3 GetExpandedNode(NativeArray<SubAreaNode> nodes, int index, float expandAmount, bool isComplete, bool isCounterClockwise)
	{
		if (!isComplete)
		{
			if (nodes.Length == 1)
			{
				return nodes[index].m_Position;
			}
			if (index == 0)
			{
				float2 xz = nodes[math.select(index + 1, 0, index == nodes.Length - 1)].m_Position.xz;
				float3 position = nodes[index].m_Position;
				float2 @float = math.normalizesafe(xz - position.xz);
				float2 float2 = math.select(MathUtils.Left(@float), MathUtils.Right(@float), isCounterClockwise) - @float;
				position.xz += float2 * expandAmount;
				return position;
			}
			if (index == nodes.Length - 1)
			{
				float2 xz2 = nodes[math.select(index - 1, nodes.Length - 1, index == 0)].m_Position.xz;
				float3 position2 = nodes[index].m_Position;
				float2 float3 = math.normalizesafe(xz2 - position2.xz);
				float2 float4 = math.select(MathUtils.Right(float3), MathUtils.Left(float3), isCounterClockwise) - float3;
				position2.xz += float4 * expandAmount;
				return position2;
			}
		}
		float2 xz3 = nodes[math.select(index - 1, nodes.Length - 1, index == 0)].m_Position.xz;
		float2 xz4 = nodes[math.select(index + 1, 0, index == nodes.Length - 1)].m_Position.xz;
		float3 position3 = nodes[index].m_Position;
		float2 float5 = math.normalizesafe(xz3 - position3.xz);
		float2 y = math.normalizesafe(xz4 - position3.xz);
		float2 float6 = math.select(MathUtils.Right(float5), MathUtils.Left(float5), isCounterClockwise);
		float num = math.acos(math.clamp(math.dot(float5, y), -1f, 1f));
		float num2 = math.sign(math.dot(float6, y));
		float num3 = math.tan(num * 0.5f);
		float6 += float5 * math.select(num2 / num3, 0f, num3 < 0.001f);
		position3.xz += float6 * expandAmount;
		return position3;
	}
```

- `public static GetExpandedNode<TNodeList>(TNodeList nodes, System.Int32 index, System.Int32 prevIndex, System.Int32 nextIndex, System.Single expandAmount, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetExpandedNode<TNodeList>(TNodeList nodes, System.Int32 index, System.Int32 prevIndex, System.Int32 nextIndex, System.Single expandAmount, System.Boolean isCounterClockwise);
```

- `public static GetMinNodeDistance(Game.Prefabs.AreaGeometryData areaData) : System.Single`  

```csharp
public static float GetMinNodeDistance(AreaType areaType)
	{
		return areaType switch
		{
			AreaType.Lot => 8f, 
			AreaType.District => 32f, 
			AreaType.MapTile => 64f, 
			AreaType.Space => 1f, 
			AreaType.Surface => 0.75f, 
			_ => 1f, 
		};
	}
```

- `public static GetMinNodeDistance(Game.Areas.AreaType areaType) : System.Single`  

```csharp
public static float GetMinNodeDistance(AreaType areaType)
	{
		return areaType switch
		{
			AreaType.Lot => 8f, 
			AreaType.District => 32f, 
			AreaType.MapTile => 64f, 
			AreaType.Space => 1f, 
			AreaType.Surface => 0.75f, 
			_ => 1f, 
		};
	}
```

- `public static GetRandomPosition(Unity.Mathematics.Random& random, Game.Areas.Geometry geometry, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles) : Unity.Mathematics.float3`  

```csharp
public static float3 GetRandomPosition(ref Unity.Mathematics.Random random, Geometry geometry, DynamicBuffer<Node> nodes, DynamicBuffer<Triangle> triangles)
	{
		float num = random.NextFloat(geometry.m_SurfaceArea);
		for (int i = 0; i < triangles.Length; i++)
		{
			Triangle3 triangle = GetTriangle3(nodes, triangles[i]);
			num -= MathUtils.Area(triangle.xz);
			if (num <= 0f)
			{
				float2 @float = random.NextFloat2(1f);
				@float = math.select(@float, 1f - @float, math.csum(@float) > 1f);
				return MathUtils.Position(triangle, @float);
			}
		}
		if (nodes.Length >= 2)
		{
			return math.lerp(nodes[0].m_Position, nodes[1].m_Position, random.NextFloat(1f));
		}
		if (nodes.Length == 1)
		{
			return nodes[0].m_Position;
		}
		return default(float3);
	}
```

- `public static GetRandomRotation(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : Unity.Mathematics.quaternion`  

```csharp
public static quaternion GetRandomRotation(ref Unity.Mathematics.Random random, float3 position, DynamicBuffer<Node> nodes)
	{
		float2 value = default(float2);
		float num = float.MaxValue;
		Line2.Segment line = default(Line2.Segment);
		line.a = nodes[nodes.Length - 1].m_Position.xz;
		for (int i = 0; i < nodes.Length; i++)
		{
			line.b = nodes[i].m_Position.xz;
			float t;
			float num2 = MathUtils.DistanceSquared(line, position.xz, out t);
			if (num2 < num)
			{
				value = line.b - line.a;
				num = num2;
			}
			line.a = line.b;
		}
		float num3;
		if (MathUtils.TryNormalize(ref value))
		{
			num3 = math.atan2(value.x, value.y);
			num3 += (float)random.NextInt(4) * (MathF.PI / 2f);
		}
		else
		{
			num3 = random.NextFloat(MathF.PI * 2f);
		}
		return quaternion.RotateY(num3);
	}
```

- `public static GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Colossal.Mathematics.Triangle2`  

```csharp
public static Triangle2 GetTriangle2(DynamicBuffer<Node> nodes, Triangle triangle, float expandAmount, bool isCounterClockwise)
	{
		Triangle2 result = default(Triangle2);
		result.a = GetExpandedNode(nodes, triangle.m_Indices.x, expandAmount, isComplete: true, isCounterClockwise).xz;
		result.b = GetExpandedNode(nodes, triangle.m_Indices.y, expandAmount, isComplete: true, isCounterClockwise).xz;
		result.c = GetExpandedNode(nodes, triangle.m_Indices.z, expandAmount, isComplete: true, isCounterClockwise).xz;
		return result;
	}
```

- `public static GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle, System.Single expandAmount, System.Boolean isCounterClockwise) : Colossal.Mathematics.Triangle2`  

```csharp
public static Triangle2 GetTriangle2(DynamicBuffer<Node> nodes, Triangle triangle, float expandAmount, bool isCounterClockwise)
	{
		Triangle2 result = default(Triangle2);
		result.a = GetExpandedNode(nodes, triangle.m_Indices.x, expandAmount, isComplete: true, isCounterClockwise).xz;
		result.b = GetExpandedNode(nodes, triangle.m_Indices.y, expandAmount, isComplete: true, isCounterClockwise).xz;
		result.c = GetExpandedNode(nodes, triangle.m_Indices.z, expandAmount, isComplete: true, isCounterClockwise).xz;
		return result;
	}
```

- `public static GetTriangle3(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Colossal.Mathematics.Triangle3`  

```csharp
public static Triangle3 GetTriangle3(DynamicBuffer<Node> nodes, Triangle triangle)
	{
		return new Triangle3(nodes[triangle.m_Indices.x].m_Position, nodes[triangle.m_Indices.y].m_Position, nodes[triangle.m_Indices.z].m_Position);
	}
```

- `public static GetTypeMask(Game.Areas.AreaType type) : Game.Areas.AreaTypeMask`  

```csharp
public static AreaTypeMask GetTypeMask(AreaType type)
	{
		if (type != AreaType.None)
		{
			return (AreaTypeMask)(1 << (int)type);
		}
		return AreaTypeMask.None;
	}
```

- `public static HasOption(Game.Prefabs.DistrictOptionData optionData, Game.Areas.DistrictOption option) : System.Boolean`  

```csharp
public static bool HasOption(DistrictOptionData optionData, DistrictOption option)
	{
		return (optionData.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```

- `public static IntersectArea(Unity.Mathematics.float3 position, System.Single radius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles) : System.Boolean`  

```csharp
public static bool IntersectArea(float3 position, float radius, DynamicBuffer<Node> nodes, DynamicBuffer<Triangle> triangles)
	{
		Circle2 circle = new Circle2(radius, position.xz);
		for (int i = 0; i < triangles.Length; i++)
		{
			if (MathUtils.Intersect(GetTriangle2(nodes, triangles[i]), circle))
			{
				return true;
			}
		}
		return false;
	}
```

- `public static IntersectEdges(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : System.Boolean`  

```csharp
public static bool IntersectEdges(float3 position, float radius, float extraRadius, DynamicBuffer<Node> nodes)
	{
		float num = radius + extraRadius;
		num *= num;
		Line2.Segment line = default(Line2.Segment);
		line.a = nodes[nodes.Length - 1].m_Position.xz;
		for (int i = 0; i < nodes.Length; i++)
		{
			line.b = nodes[i].m_Position.xz;
			if (MathUtils.DistanceSquared(line, position.xz, out var _) < num)
			{
				return true;
			}
			line.a = line.b;
		}
		return false;
	}
```

- `public static IntersectObjects(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride = False) : System.Boolean`  

```csharp
public static bool IntersectObjects(float3 position, float radius, float extraRadius, NativeList<ObjectItem> objects, bool canOverride = false)
	{
		if (objects.IsCreated)
		{
			float num = (radius + extraRadius) * 0.5f;
			for (int i = 0; i < objects.Length; i++)
			{
				ObjectItem objectItem = objects[i];
				if (!canOverride || !(objectItem.m_Circle.radius < num))
				{
					float num2 = radius + objectItem.m_Circle.radius;
					if (math.distancesq(position.xz, objectItem.m_Circle.position) < num2 * num2)
					{
						return true;
					}
				}
			}
		}
		return false;
	}
```

- `public static IsEdge(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Unity.Mathematics.bool3`  

```csharp
public static bool3 IsEdge(DynamicBuffer<Node> nodes, Triangle triangle)
	{
		int3 @int = math.abs(triangle.m_Indices - triangle.m_Indices.yzx);
		return (@int == 1) | (@int == nodes.Length - 1);
	}
```

- `public static SelectAreaPrefab(Unity.Entities.DynamicBuffer<Game.Prefabs.PlaceholderObjectElement> placeholderElements, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> spawnableDatas, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> selectedSpawnables, Unity.Mathematics.Random& random, Unity.Entities.Entity& result, System.Int32& seed) : System.Boolean`  

```csharp
public static bool SelectAreaPrefab(DynamicBuffer<PlaceholderObjectElement> placeholderElements, ComponentLookup<SpawnableObjectData> spawnableDatas, NativeParallelHashMap<Entity, int> selectedSpawnables, ref Unity.Mathematics.Random random, out Entity result, out int seed)
	{
		int num = 0;
		bool flag = false;
		result = Entity.Null;
		seed = 0;
		for (int i = 0; i < placeholderElements.Length; i++)
		{
			PlaceholderObjectElement placeholderObjectElement = placeholderElements[i];
			SpawnableObjectData spawnableObjectData = spawnableDatas[placeholderObjectElement.m_Object];
			int item = 0;
			if (selectedSpawnables.IsCreated && selectedSpawnables.TryGetValue(placeholderObjectElement.m_Object, out item))
			{
				if (!flag)
				{
					num = 0;
					flag = true;
				}
			}
			else if (flag)
			{
				continue;
			}
			num += spawnableObjectData.m_Probability;
			if (random.NextInt(num) < spawnableObjectData.m_Probability)
			{
				result = placeholderObjectElement.m_Object;
				seed = (flag ? item : random.NextInt());
			}
		}
		if (result != Entity.Null)
		{
			if (!flag && selectedSpawnables.IsCreated)
			{
				selectedSpawnables.Add(result, seed);
			}
			return true;
		}
		return false;
	}
```

- `public static SetCollisionFlags(Game.Prefabs.AreaGeometryData& areaGeometryData, System.Boolean ignoreMarkers) : System.Void`  

```csharp
public static void SetCollisionFlags(ref AreaGeometryData areaGeometryData, bool ignoreMarkers)
	{
		if (!ignoreMarkers)
		{
			AreaType type = areaGeometryData.m_Type;
			if ((uint)(type - 3) <= 1u)
			{
				areaGeometryData.m_Flags |= GeometryFlags.PhysicalGeometry;
			}
		}
	}
```

- `public static TryFitInside(Unity.Mathematics.float3& position, System.Single radius, System.Single extraRadius, Game.Areas.Area area, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride = False) : System.Boolean`  

```csharp
public static bool TryFitInside(ref float3 position, float radius, float extraRadius, Area area, DynamicBuffer<Node> nodes, NativeList<ObjectItem> objects, bool canOverride = false)
	{
		float num = radius + extraRadius;
		num *= num;
		bool flag = false;
		Line2.Segment line = default(Line2.Segment);
		line.a = nodes[nodes.Length - 1].m_Position.xz;
		for (int i = 0; i < nodes.Length; i++)
		{
			line.b = nodes[i].m_Position.xz;
			if (MathUtils.DistanceSquared(line, position.xz, out var t) < num)
			{
				float2 @float = math.normalizesafe(line.b - line.a);
				float2 y = position.xz - MathUtils.Position(line, t);
				float num2 = math.dot(@float, y);
				@float = (((area.m_Flags & AreaFlags.CounterClockwise) == 0) ? MathUtils.Right(@float) : MathUtils.Left(@float));
				@float *= math.sqrt(num - num2 * num2) - math.dot(@float, y) + 0.01f;
				position.xz += @float;
				flag = true;
			}
			line.a = line.b;
		}
		if (objects.IsCreated)
		{
			float num3 = (radius + extraRadius) * 0.5f;
			for (int j = 0; j < objects.Length; j++)
			{
				ObjectItem objectItem = objects[j];
				if (!canOverride || !(objectItem.m_Circle.radius < num3))
				{
					float num4 = radius + objectItem.m_Circle.radius;
					float num5 = math.distancesq(position.xz, objectItem.m_Circle.position);
					if (num5 < num4 * num4)
					{
						float num6 = math.sqrt(num5);
						float2 float2 = (objectItem.m_Circle.position - position.xz) * (num4 / num6 - 1f);
						position.xz += float2;
						flag = true;
					}
				}
			}
		}
		if (flag)
		{
			if (!IntersectEdges(position, radius, extraRadius, nodes))
			{
				return !IntersectObjects(position, radius, extraRadius, objects, canOverride);
			}
			return false;
		}
		return true;
	}
```

- `public static TryGetRandomObjectLocation(Unity.Mathematics.Random& random, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Areas.Area area, Game.Areas.Geometry geometry, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, Game.Objects.Transform& transform) : System.Boolean`  

```csharp
public static bool TryGetRandomObjectLocation(ref Unity.Mathematics.Random random, ObjectGeometryData objectGeometryData, Area area, Geometry geometry, float extraRadius, DynamicBuffer<Node> nodes, DynamicBuffer<Triangle> triangles, NativeList<ObjectItem> objects, out Game.Objects.Transform transform)
	{
		transform.m_Position = GetRandomPosition(ref random, geometry, nodes, triangles);
		float num = (((objectGeometryData.m_Flags & Game.Objects.GeometryFlags.Circular) == 0) ? (math.length(MathUtils.Size(objectGeometryData.m_Bounds.xz)) * 0.5f) : (objectGeometryData.m_Size.x * 0.5f));
		bool result = TryFitInside(ref transform.m_Position, num, extraRadius, area, nodes, objects, canOverride: true);
		if (objects.IsCreated)
		{
			float num2 = (num + extraRadius) * 0.5f;
			int num3 = 0;
			for (int i = 0; i < objects.Length; i++)
			{
				ObjectItem value = objects[i];
				if (value.m_Circle.radius < num2)
				{
					float num4 = num + value.m_Circle.radius;
					if (math.distancesq(transform.m_Position.xz, value.m_Circle.position) < num4 * num4)
					{
						objects[num3++] = value;
					}
				}
			}
			if (num3 < objects.Length)
			{
				objects.RemoveRange(num3, objects.Length - num3);
			}
		}
		transform.m_Rotation = GetRandomRotation(ref random, transform.m_Position, nodes);
		if ((objectGeometryData.m_Flags & Game.Objects.GeometryFlags.Circular) == 0)
		{
			transform.m_Position.xz -= math.rotate(transform.m_Rotation, MathUtils.Center(objectGeometryData.m_Bounds)).xz;
		}
		return result;
	}
```


## Nested types

- `Game.Areas.AreaUtils+ObjectItem`  
- `Game.Areas.AreaUtils+FixPathItem`  

