# Game.Net.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    private static System.Boolean CheckGeometryShape(Game.Net.EdgeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds);
    private static System.Boolean CheckGeometryShape(Game.Net.EdgeNodeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds);
    private static System.Boolean CheckSegmentShape(Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds);
    private static System.Boolean CheckSurface(Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Prefabs.NetCompositionData compositionData, Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds);
    private static System.Boolean FindConnectedLane(Unity.Entities.Entity owner, Unity.Entities.Entity ignore, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data);
    private static System.Boolean FindConnectedLane(Unity.Entities.Entity owner, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data);
    private static Unity.Entities.Entity GetNetNode(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data);
    private static Unity.Entities.Entity GetOwner(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edge);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    private static System.Boolean IsIgnored(Unity.Entities.Entity edge, Unity.Entities.Entity node, Game.Tools.ValidationSystem+EntityData data, Game.Net.TrackTypes trackTypes, System.Boolean isSource, System.Boolean isTarget);
    private static System.Boolean IsInternal(Unity.Entities.Entity topLevelEntity, Unity.Entities.Entity node, Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Game.Tools.ValidationSystem+EntityData data);
    public static System.Boolean QuadCylinderIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadCylinderIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds1 height2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadCylinderIntersectHelper(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Boolean QuadIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Boolean QuadTriangleIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadTriangleIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadTriangleIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static Colossal.Mathematics.Bounds3 SetHeightRange(Colossal.Mathematics.Bounds3 bounds, Colossal.Mathematics.Bounds1 heightRange);
    public static System.Boolean TriangleCylinderIntersect(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean TriangleCylinderIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Void ValidateEdge(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Net.Fixed _fixed, Game.Net.Edge edge, Game.Net.EdgeGeometry edgeGeometry, Game.Net.StartNodeGeometry startNodeGeometry, Game.Net.EndNodeGeometry endNodeGeometry, Game.Net.Composition composition, Game.Prefabs.PrefabRef prefabRef, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Collections.NativeList<Game.Net.ConnectedNode> tempNodes);
    public static System.Void ValidateLane(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Net.Lane lane, Game.Net.TrackLane trackLane, Game.Net.Curve curve, Game.Net.EdgeLane edgeLane, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Methods

- `private static CheckGeometryShape(Game.Net.EdgeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds) : System.Boolean`  

```csharp
private static bool CheckGeometryShape(EdgeNodeGeometry geometry, ref Bounds3 errorBounds)
	{
		if (math.any(geometry.m_Left.m_Length > 0.05f) | math.any(geometry.m_Right.m_Length > 0.05f))
		{
			return CheckSegmentShape(geometry.m_Left, ref errorBounds) | CheckSegmentShape(geometry.m_Right, ref errorBounds);
		}
		return false;
	}
```

- `private static CheckGeometryShape(Game.Net.EdgeNodeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds) : System.Boolean`  

```csharp
private static bool CheckGeometryShape(EdgeNodeGeometry geometry, ref Bounds3 errorBounds)
	{
		if (math.any(geometry.m_Left.m_Length > 0.05f) | math.any(geometry.m_Right.m_Length > 0.05f))
		{
			return CheckSegmentShape(geometry.m_Left, ref errorBounds) | CheckSegmentShape(geometry.m_Right, ref errorBounds);
		}
		return false;
	}
```

- `private static CheckSegmentShape(Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds) : System.Boolean`  

```csharp
private static bool CheckSegmentShape(Segment segment, ref Bounds3 errorBounds)
	{
		bool result = false;
		Quad3 quad = default(Quad3);
		quad.a = segment.m_Left.a;
		quad.b = segment.m_Right.a;
		float3 y = quad.b - quad.a;
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment.m_Left, t);
			quad.c = MathUtils.Position(segment.m_Right, t);
			float3 @float = quad.d - quad.a;
			float3 float2 = quad.c - quad.b;
			float3 float3 = quad.c - quad.d;
			@float = math.select(@float, 0f, math.lengthsq(@float) < 0.0001f);
			float2 = math.select(float2, 0f, math.lengthsq(float2) < 0.0001f);
			if ((math.cross(@float, y).y < 0f) | (math.cross(float2, float3).y < 0f))
			{
				errorBounds |= MathUtils.Bounds(quad);
				result = true;
			}
			quad.a = quad.d;
			quad.b = quad.c;
			y = float3;
		}
		return result;
	}
```

- `private static CheckSurface(Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Prefabs.NetCompositionData compositionData, Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds) : System.Boolean`  

```csharp
private static bool CheckSurface(WaterSurfaceData waterSurfaceData, TerrainHeightData terrainHeightData, PlaceableNetData placeableNetData, NetCompositionData compositionData, Segment segment, ref Bounds3 errorBounds)
	{
		bool result = false;
		bool flag = (placeableNetData.m_PlacementFlags & (PlacementFlags.OnGround | PlacementFlags.Floating)) == PlacementFlags.Floating;
		bool flag2 = (placeableNetData.m_PlacementFlags & (PlacementFlags.OnGround | PlacementFlags.Floating | PlacementFlags.ShoreLine)) == PlacementFlags.OnGround;
		flag2 &= (compositionData.m_Flags.m_General & CompositionFlags.General.Tunnel) == 0;
		if (flag || flag2)
		{
			float sampleInterval = WaterUtils.GetSampleInterval(ref waterSurfaceData);
			int num = (int)math.ceil(segment.middleLength / sampleInterval);
			for (int i = 0; i < num; i++)
			{
				float t = ((float)i + 0.5f) / (float)num;
				float3 @float = MathUtils.Position(segment.m_Left, t);
				float3 float2 = MathUtils.Position(segment.m_Right, t);
				int num2 = (int)math.ceil(math.distance(@float, float2) / sampleInterval);
				for (int j = 0; j < num2; j++)
				{
					float t2 = ((float)j + 0.5f) / (float)num2;
					float3 float3 = math.lerp(@float, float2, t2);
					float num3 = WaterUtils.SampleDepth(ref waterSurfaceData, float3);
					if (flag2 && num3 >= 0.2f && WaterUtils.SampleHeight(ref waterSurfaceData, ref terrainHeightData, float3) > float3.y + compositionData.m_HeightRange.min)
					{
						errorBounds |= float3;
						result = true;
					}
					if (flag && num3 < 0.2f)
					{
						errorBounds |= float3;
						result = true;
					}
				}
			}
		}
		return result;
	}
```

- `private static FindConnectedLane(Unity.Entities.Entity owner, Unity.Entities.Entity ignore, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data) : System.Boolean`  

```csharp
private static bool FindConnectedLane(Entity owner, PathNode node, ValidationSystem.EntityData data)
	{
		DynamicBuffer<SubLane> dynamicBuffer = data.m_Lanes[owner];
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			Lane lane = data.m_Lane[dynamicBuffer[i].m_SubLane];
			if (lane.m_StartNode.Equals(node) || lane.m_EndNode.Equals(node))
			{
				return true;
			}
		}
		return false;
	}
```

- `private static FindConnectedLane(Unity.Entities.Entity owner, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data) : System.Boolean`  

```csharp
private static bool FindConnectedLane(Entity owner, PathNode node, ValidationSystem.EntityData data)
	{
		DynamicBuffer<SubLane> dynamicBuffer = data.m_Lanes[owner];
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			Lane lane = data.m_Lane[dynamicBuffer[i].m_SubLane];
			if (lane.m_StartNode.Equals(node) || lane.m_EndNode.Equals(node))
			{
				return true;
			}
		}
		return false;
	}
```

- `private static GetNetNode(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data) : Unity.Entities.Entity`  

```csharp
private static Entity GetNetNode(Entity entity, ValidationSystem.EntityData data)
	{
		if (data.m_Temp.TryGetComponent(entity, out var componentData))
		{
			return componentData.m_Original;
		}
		return entity;
	}
```

- `private static GetOwner(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edge) : Unity.Entities.Entity`  

```csharp
private static Entity GetOwner(Entity entity, ValidationSystem.EntityData data, out Entity assetStamp, out Entity edge)
	{
		assetStamp = Entity.Null;
		edge = Entity.Null;
		Owner componentData;
		while (data.m_Owner.TryGetComponent(entity, out componentData) && !data.m_Building.HasComponent(entity))
		{
			if (data.m_AssetStamp.HasComponent(componentData.m_Owner))
			{
				assetStamp = componentData.m_Owner;
				break;
			}
			if (data.m_Edge.HasComponent(componentData.m_Owner))
			{
				edge = componentData.m_Owner;
			}
			entity = componentData.m_Owner;
			if (data.m_Temp.HasComponent(entity))
			{
				entity = data.m_Temp[entity].m_Original;
			}
		}
		return entity;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `public static Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static bool Intersect(Segment segment1, Segment segment2, NetCompositionData prefabCompositionData1, NetCompositionData prefabCompositionData2, ref Bounds2 intersection)
	{
		Bounds2 xz = (MathUtils.Bounds(segment1.m_Left) | MathUtils.Bounds(segment1.m_Right)).xz;
		Bounds2 xz2 = (MathUtils.Bounds(segment2.m_Left) | MathUtils.Bounds(segment2.m_Right)).xz;
		if (!MathUtils.Intersect(xz, xz2))
		{
			return false;
		}
		bool result = false;
		Quad2 quad = default(Quad2);
		quad.a = segment1.m_Left.a.xz;
		quad.b = segment1.m_Right.a.xz;
		Bounds2 bounds = MathUtils.Bounds(quad.a, quad.b);
		Quad2 quad2 = default(Quad2);
		for (int i = 1; i <= 8; i++)
		{
			float t = (float)i / 8f;
			quad.d = MathUtils.Position(segment1.m_Left, t).xz;
			quad.c = MathUtils.Position(segment1.m_Right, t).xz;
			Bounds2 bounds2 = MathUtils.Bounds(quad.d, quad.c);
			Bounds2 bounds3 = bounds | bounds2;
			if (MathUtils.Intersect(bounds3, xz2))
			{
				quad2.a = segment2.m_Left.a.xz;
				quad2.b = segment2.m_Right.a.xz;
				Bounds2 bounds4 = MathUtils.Bounds(quad2.a, quad2.b);
				for (int j = 1; j <= 8; j++)
				{
					float t2 = (float)j / 8f;
					quad2.d = MathUtils.Position(segment2.m_Left, t2).xz;
					quad2.c = MathUtils.Position(segment2.m_Right, t2).xz;
					Bounds2 bounds5 = MathUtils.Bounds(quad2.d, quad2.c);
					Bounds2 bounds6 = bounds4 | bounds5;
					if (MathUtils.Intersect(bounds3, bounds6) && MathUtils.Intersect(quad, quad2, out var intersection2))
					{
						result = true;
						intersection |= intersection2;
					}
					quad2.a = quad2.d;
					quad2.b = quad2.c;
					bounds4 = bounds5;
				}
			}
			quad.a = quad.d;
			quad.b = quad.c;
			bounds = bounds2;
		}
		return result;
	}
```

- `private static IsIgnored(Unity.Entities.Entity edge, Unity.Entities.Entity node, Game.Tools.ValidationSystem+EntityData data, Game.Net.TrackTypes trackTypes, System.Boolean isSource, System.Boolean isTarget) : System.Boolean`  

```csharp
private static bool IsIgnored(Entity edge, Entity node, ValidationSystem.EntityData data, TrackTypes trackTypes, bool isSource, bool isTarget)
	{
		EdgeIterator edgeIterator = new EdgeIterator(edge, node, data.m_ConnectedEdges, data.m_Edge, data.m_Temp, data.m_Hidden);
		EdgeIteratorValue value;
		while (edgeIterator.GetNext(out value))
		{
			if (value.m_Edge == edge || !data.m_Lanes.TryGetBuffer(value.m_Edge, out var bufferData))
			{
				continue;
			}
			for (int i = 0; i < bufferData.Length; i++)
			{
				Entity subLane = bufferData[i].m_SubLane;
				if (!data.m_TrackLane.TryGetComponent(subLane, out var componentData))
				{
					continue;
				}
				PrefabRef prefabRef = data.m_PrefabRef[subLane];
				if (data.m_TrackLaneData[prefabRef.m_Prefab].m_TrackTypes == trackTypes)
				{
					bool num = (componentData.m_Flags & TrackLaneFlags.Twoway) != 0;
					bool flag = (componentData.m_Flags & TrackLaneFlags.Invert) != 0;
					bool flag2 = num | (value.m_End != flag);
					bool flag3 = num | (value.m_End == flag);
					if ((isSource && flag3) || (isTarget && flag2))
					{
						return false;
					}
				}
			}
		}
		return true;
	}
```

- `private static IsInternal(Unity.Entities.Entity topLevelEntity, Unity.Entities.Entity node, Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Game.Tools.ValidationSystem+EntityData data) : System.Boolean`  

```csharp
private static bool IsInternal(Entity topLevelEntity, Entity node, DynamicBuffer<ConnectedEdge> connectedEdges, ValidationSystem.EntityData data)
	{
		for (int i = 0; i < connectedEdges.Length; i++)
		{
			Entity entity = connectedEdges[i].m_Edge;
			Edge edge = data.m_Edge[entity];
			if (!(edge.m_Start == node) && !(edge.m_End == node))
			{
				continue;
			}
			while (data.m_Owner.HasComponent(entity) && !data.m_Building.HasComponent(entity))
			{
				Entity owner = data.m_Owner[entity].m_Owner;
				if (data.m_AssetStamp.HasComponent(owner))
				{
					break;
				}
				entity = owner;
			}
			if (topLevelEntity != entity)
			{
				return false;
			}
		}
		return true;
	}
```

- `public static QuadCylinderIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static bool QuadCylinderIntersect(Quad3 quad1, Cylinder3 cylinder2, out Bounds3 intersection1, out Bounds3 intersection2)
	{
		intersection1.min = float.MaxValue;
		intersection1.max = float.MinValue;
		intersection2.min = float.MaxValue;
		intersection2.max = float.MinValue;
		Line3.Segment line = new Line3.Segment(quad1.a, quad1.b);
		Line3.Segment line2 = new Line3.Segment(quad1.b, quad1.c);
		Line3.Segment line3 = new Line3.Segment(quad1.c, quad1.d);
		Line3.Segment line4 = new Line3.Segment(quad1.d, quad1.a);
		float3 @float = math.mul(cylinder2.rotation, new float3(cylinder2.circle.position.x, cylinder2.height.min, cylinder2.circle.position.y));
		float3 float2 = math.mul(cylinder2.rotation, new float3(cylinder2.circle.position.x, cylinder2.height.max, cylinder2.circle.position.y));
		Circle2 circle = cylinder2.circle;
		circle.position = @float.xz;
		Bounds1 height = MathUtils.Bounds(@float.y, float2.y);
		Line3 line5 = default(Line3);
		line5.a = new float3(circle.position.x, height.min, circle.position.y);
		line5.b = new float3(circle.position.x, height.max, circle.position.y);
		return QuadCylinderIntersectHelper(line, circle, height, ref intersection1, ref intersection2) | QuadCylinderIntersectHelper(line2, circle, height, ref intersection1, ref intersection2) | QuadCylinderIntersectHelper(line3, circle, height, ref intersection1, ref intersection2) | QuadCylinderIntersectHelper(line4, circle, height, ref intersection1, ref intersection2) | QuadCylinderIntersectHelper(quad1, line5, ref intersection1, ref intersection2);
	}
```

- `private static QuadCylinderIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds1 height2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static bool QuadCylinderIntersectHelper(Quad3 quad1, Line3 line2, ref Bounds3 intersection1, ref Bounds3 intersection2)
	{
		if (MathUtils.Intersect(quad1, line2, out var t))
		{
			intersection1 |= MathUtils.Position(line2, t);
			intersection2 |= MathUtils.Position(line2, math.saturate(t));
			return true;
		}
		return false;
	}
```

- `private static QuadCylinderIntersectHelper(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static bool QuadCylinderIntersectHelper(Quad3 quad1, Line3 line2, ref Bounds3 intersection1, ref Bounds3 intersection2)
	{
		if (MathUtils.Intersect(quad1, line2, out var t))
		{
			intersection1 |= MathUtils.Position(line2, t);
			intersection2 |= MathUtils.Position(line2, math.saturate(t));
			return true;
		}
		return false;
	}
```

- `public static QuadIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static bool QuadIntersect(Quad3 quad1, Quad3 quad2, out Bounds3 intersection1, out Bounds3 intersection2)
	{
		intersection1.min = float.MaxValue;
		intersection1.max = float.MinValue;
		intersection2.min = float.MaxValue;
		intersection2.max = float.MinValue;
		Triangle3 triangle = new Triangle3(quad1.a, quad1.d, quad1.c);
		Triangle3 triangle2 = new Triangle3(quad1.c, quad1.b, quad1.a);
		Triangle3 triangle3 = new Triangle3(quad2.a, quad2.d, quad2.c);
		Triangle3 triangle4 = new Triangle3(quad2.c, quad2.b, quad2.a);
		Line3.Segment line = new Line3.Segment(quad1.a, quad1.b);
		Line3.Segment line2 = new Line3.Segment(quad1.b, quad1.c);
		Line3.Segment line3 = new Line3.Segment(quad1.c, quad1.d);
		Line3.Segment line4 = new Line3.Segment(quad1.d, quad1.a);
		return QuadIntersectHelper(triangle, quad2, ref intersection1, ref intersection2) | QuadIntersectHelper(triangle2, quad2, ref intersection1, ref intersection2) | QuadIntersectHelper(triangle3, quad1, ref intersection2, ref intersection1) | QuadIntersectHelper(triangle4, quad1, ref intersection2, ref intersection1) | QuadIntersectHelper(line, quad2, ref intersection1, ref intersection2) | QuadIntersectHelper(line2, quad2, ref intersection1, ref intersection2) | QuadIntersectHelper(line3, quad2, ref intersection1, ref intersection2) | QuadIntersectHelper(line4, quad2, ref intersection1, ref intersection2);
	}
```

- `private static QuadIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static bool QuadIntersectHelper(Line3.Segment line1, Quad3 quad2, ref Bounds3 intersection1, ref Bounds3 intersection2)
	{
		Line2.Segment xz = line1.xz;
		bool result = false;
		if (MathUtils.Intersect(xz, new Line2.Segment(quad2.a.xz, quad2.b.xz), out var t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(quad2.a, quad2.b, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(quad2.b.xz, quad2.c.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(quad2.b, quad2.c, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(quad2.c.xz, quad2.d.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(quad2.c, quad2.d, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(quad2.d.xz, quad2.a.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(quad2.d, quad2.a, t.y);
			result = true;
		}
		return result;
	}
```

- `private static QuadIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static bool QuadIntersectHelper(Line3.Segment line1, Quad3 quad2, ref Bounds3 intersection1, ref Bounds3 intersection2)
	{
		Line2.Segment xz = line1.xz;
		bool result = false;
		if (MathUtils.Intersect(xz, new Line2.Segment(quad2.a.xz, quad2.b.xz), out var t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(quad2.a, quad2.b, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(quad2.b.xz, quad2.c.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(quad2.b, quad2.c, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(quad2.c.xz, quad2.d.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(quad2.c, quad2.d, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(quad2.d.xz, quad2.a.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(quad2.d, quad2.a, t.y);
			result = true;
		}
		return result;
	}
```

- `public static QuadTriangleIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static bool QuadTriangleIntersect(Quad3 quad1, Triangle3 triangle2, out Bounds3 intersection1, out Bounds3 intersection2)
	{
		intersection1.min = float.MaxValue;
		intersection1.max = float.MinValue;
		intersection2.min = float.MaxValue;
		intersection2.max = float.MinValue;
		Triangle3 triangle3 = new Triangle3(quad1.a, quad1.d, quad1.c);
		Triangle3 triangle4 = new Triangle3(quad1.c, quad1.b, quad1.a);
		Line3.Segment line = new Line3.Segment(quad1.a, quad1.b);
		Line3.Segment line2 = new Line3.Segment(quad1.b, quad1.c);
		Line3.Segment line3 = new Line3.Segment(quad1.c, quad1.d);
		Line3.Segment line4 = new Line3.Segment(quad1.d, quad1.a);
		return QuadTriangleIntersectHelper(triangle3, triangle2, ref intersection1, ref intersection2) | QuadTriangleIntersectHelper(triangle4, triangle2, ref intersection1, ref intersection2) | QuadIntersectHelper(triangle2, quad1, ref intersection2, ref intersection1) | QuadTriangleIntersectHelper(line, triangle2, ref intersection1, ref intersection2) | QuadTriangleIntersectHelper(line2, triangle2, ref intersection1, ref intersection2) | QuadTriangleIntersectHelper(line3, triangle2, ref intersection1, ref intersection2) | QuadTriangleIntersectHelper(line4, triangle2, ref intersection1, ref intersection2);
	}
```

- `private static QuadTriangleIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static bool QuadTriangleIntersectHelper(Line3.Segment line1, Triangle3 triangle2, ref Bounds3 intersection1, ref Bounds3 intersection2)
	{
		Line2.Segment xz = line1.xz;
		bool result = false;
		if (MathUtils.Intersect(xz, new Line2.Segment(triangle2.a.xz, triangle2.b.xz), out var t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(triangle2.a, triangle2.b, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(triangle2.b.xz, triangle2.c.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(triangle2.b, triangle2.c, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(triangle2.c.xz, triangle2.a.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(triangle2.c, triangle2.a, t.y);
			result = true;
		}
		return result;
	}
```

- `private static QuadTriangleIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static bool QuadTriangleIntersectHelper(Line3.Segment line1, Triangle3 triangle2, ref Bounds3 intersection1, ref Bounds3 intersection2)
	{
		Line2.Segment xz = line1.xz;
		bool result = false;
		if (MathUtils.Intersect(xz, new Line2.Segment(triangle2.a.xz, triangle2.b.xz), out var t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(triangle2.a, triangle2.b, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(triangle2.b.xz, triangle2.c.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(triangle2.b, triangle2.c, t.y);
			result = true;
		}
		if (MathUtils.Intersect(xz, new Line2.Segment(triangle2.c.xz, triangle2.a.xz), out t))
		{
			intersection1 |= MathUtils.Position(line1, t.x);
			intersection2 |= math.lerp(triangle2.c, triangle2.a, t.y);
			result = true;
		}
		return result;
	}
```

- `public static SetHeightRange(Colossal.Mathematics.Bounds3 bounds, Colossal.Mathematics.Bounds1 heightRange) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 SetHeightRange(Bounds3 bounds, Bounds1 heightRange)
	{
		bounds.min.y += heightRange.min;
		bounds.max.y += heightRange.max;
		return bounds;
	}
```

- `public static TriangleCylinderIntersect(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static bool TriangleCylinderIntersect(Triangle3 triangle1, Cylinder3 cylinder2, out Bounds3 intersection1, out Bounds3 intersection2)
	{
		intersection1.min = float.MaxValue;
		intersection1.max = float.MinValue;
		intersection2.min = float.MaxValue;
		intersection2.max = float.MinValue;
		Line3.Segment line = new Line3.Segment(triangle1.a, triangle1.b);
		Line3.Segment line2 = new Line3.Segment(triangle1.b, triangle1.c);
		Line3.Segment line3 = new Line3.Segment(triangle1.c, triangle1.a);
		float3 @float = math.mul(cylinder2.rotation, new float3(cylinder2.circle.position.x, cylinder2.height.min, cylinder2.circle.position.y));
		float3 float2 = math.mul(cylinder2.rotation, new float3(cylinder2.circle.position.x, cylinder2.height.max, cylinder2.circle.position.y));
		Circle2 circle = cylinder2.circle;
		circle.position = @float.xz;
		Bounds1 height = MathUtils.Bounds(@float.y, float2.y);
		Line3 line4 = default(Line3);
		line4.a = new float3(circle.position.x, height.min, circle.position.y);
		line4.b = new float3(circle.position.x, height.max, circle.position.y);
		return QuadCylinderIntersectHelper(line, circle, height, ref intersection1, ref intersection2) | QuadCylinderIntersectHelper(line2, circle, height, ref intersection1, ref intersection2) | QuadCylinderIntersectHelper(line3, circle, height, ref intersection1, ref intersection2) | TriangleCylinderIntersectHelper(triangle1, line4, ref intersection1, ref intersection2);
	}
```

- `private static TriangleCylinderIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static bool TriangleCylinderIntersectHelper(Triangle3 triangle1, Line3 line2, ref Bounds3 intersection1, ref Bounds3 intersection2)
	{
		if (MathUtils.Intersect(triangle1, line2, out var t))
		{
			intersection1 |= MathUtils.Position(line2, t.z);
			intersection2 |= MathUtils.Position(line2, math.saturate(t.z));
			return true;
		}
		return false;
	}
```

- `public static ValidateEdge(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Net.Fixed _fixed, Game.Net.Edge edge, Game.Net.EdgeGeometry edgeGeometry, Game.Net.StartNodeGeometry startNodeGeometry, Game.Net.EndNodeGeometry endNodeGeometry, Game.Net.Composition composition, Game.Prefabs.PrefabRef prefabRef, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Collections.NativeList<Game.Net.ConnectedNode> tempNodes) : System.Void`  

```csharp
public static void ValidateEdge(Entity entity, Temp temp, Owner owner, Fixed _fixed, Edge edge, EdgeGeometry edgeGeometry, StartNodeGeometry startNodeGeometry, EndNodeGeometry endNodeGeometry, Composition composition, PrefabRef prefabRef, bool editorMode, ValidationSystem.EntityData data, NativeList<ValidationSystem.BoundsData> edgeList, NativeQuadTree<Entity, QuadTreeBoundsXZ> objectSearchTree, NativeQuadTree<Entity, QuadTreeBoundsXZ> netSearchTree, NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ> areaSearchTree, WaterSurfaceData waterSurfaceData, TerrainHeightData terrainHeightData, NativeQueue<ErrorData>.ParallelWriter errorQueue, NativeList<ConnectedNode> tempNodes)
	{
		Edge originalNodes = default(Edge);
		originalNodes.m_Start = GetNetNode(edge.m_Start, data);
		originalNodes.m_End = GetNetNode(edge.m_End, data);
		DynamicBuffer<ConnectedNode> dynamicBuffer = data.m_ConnectedNodes[entity];
		tempNodes.Clear();
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			ConnectedNode value = dynamicBuffer[i];
			value.m_Node = GetNetNode(value.m_Node, data);
			tempNodes.Add(in value);
		}
		bool flag = owner.m_Owner != Entity.Null;
		Bounds3 bounds = edgeGeometry.m_Bounds | startNodeGeometry.m_Geometry.m_Bounds | endNodeGeometry.m_Geometry.m_Bounds;
		NetCompositionData netCompositionData = data.m_PrefabComposition[composition.m_Edge];
		NetCompositionData netCompositionData2 = data.m_PrefabComposition[composition.m_StartNode];
		NetCompositionData netCompositionData3 = data.m_PrefabComposition[composition.m_EndNode];
		CollisionMask collisionMask = NetUtils.GetCollisionMask(netCompositionData, !editorMode || flag);
		CollisionMask collisionMask2 = NetUtils.GetCollisionMask(netCompositionData2, !editorMode || flag);
		CollisionMask collisionMask3 = NetUtils.GetCollisionMask(netCompositionData3, !editorMode || flag);
		CollisionMask collisionMask4 = collisionMask | collisionMask2 | collisionMask3;
		DynamicBuffer<NetCompositionArea> edgeCompositionAreas = data.m_PrefabCompositionAreas[composition.m_Edge];
		DynamicBuffer<NetCompositionArea> startCompositionAreas = data.m_PrefabCompositionAreas[composition.m_StartNode];
		DynamicBuffer<NetCompositionArea> endCompositionAreas = data.m_PrefabCompositionAreas[composition.m_EndNode];
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
		Edge componentData;
		bool flag2 = data.m_Edge.TryGetComponent(owner.m_Owner, out componentData);
		Edge ownerEdge = default(Edge);
		if (flag2)
		{
			ownerEdge.m_Start = GetNetNode(componentData.m_Start, data);
			ownerEdge.m_End = GetNetNode(componentData.m_End, data);
		}
		Edge nodeOwners = default(Edge);
		Edge nodeAssetStamps = default(Edge);
		Edge nodeEdges = default(Edge);
		nodeOwners.m_Start = GetOwner(originalNodes.m_Start, data, out nodeAssetStamps.m_Start, out nodeEdges.m_Start);
		nodeOwners.m_End = GetOwner(originalNodes.m_End, data, out nodeAssetStamps.m_End, out nodeEdges.m_End);
		NetIterator iterator = default(NetIterator);
		if ((temp.m_Flags & TempFlags.Delete) == 0)
		{
			iterator = new NetIterator
			{
				m_Edge = edge,
				m_OwnerEdge = ownerEdge,
				m_OriginalNodes = originalNodes,
				m_NodeOwners = nodeOwners,
				m_ConnectedNodes = dynamicBuffer.AsNativeArray(),
				m_OriginalConnectedNodes = tempNodes.AsArray(),
				m_TopLevelEntity = entity2,
				m_Essential = ((temp.m_Flags & TempFlags.Essential) != 0),
				m_EditorMode = editorMode,
				m_EdgeEntity = entity,
				m_OriginalEntity = temp.m_Original,
				m_Bounds = bounds,
				m_EdgeGeometryData = edgeGeometry,
				m_StartNodeGeometryData = startNodeGeometry,
				m_EndNodeGeometryData = endNodeGeometry,
				m_EdgeCompositionData = netCompositionData,
				m_StartCompositionData = netCompositionData2,
				m_EndCompositionData = netCompositionData3,
				m_EdgeCollisionMask = collisionMask,
				m_StartCollisionMask = collisionMask2,
				m_EndCollisionMask = collisionMask3,
				m_CombinedCollisionMask = collisionMask4,
				m_Data = data,
				m_ErrorQueue = errorQueue
			};
			netSearchTree.Iterate(ref iterator);
		}
		ObjectIterator objectIterator = default(ObjectIterator);
		if ((temp.m_Flags & TempFlags.Delete) == 0)
		{
			Entity assetStamp;
			Entity edge2;
			Entity owner3 = GetOwner(entity, data, out assetStamp, out edge2);
			objectIterator = new ObjectIterator
			{
				m_OriginalNodes = originalNodes,
				m_NodeOwners = nodeOwners,
				m_NodeAssetStamps = nodeAssetStamps,
				m_NodeEdges = nodeEdges,
				m_OwnerEdge = ownerEdge,
				m_EdgeEntity = entity,
				m_TopLevelEntity = owner3,
				m_AssetStampEntity = assetStamp,
				m_Bounds = bounds,
				m_EdgeGeometryData = edgeGeometry,
				m_StartNodeGeometryData = startNodeGeometry,
				m_EndNodeGeometryData = endNodeGeometry,
				m_EdgeCompositionData = netCompositionData,
				m_StartCompositionData = netCompositionData2,
				m_EndCompositionData = netCompositionData3,
				m_EdgeCollisionMask = collisionMask,
				m_StartCollisionMask = collisionMask2,
				m_EndCollisionMask = collisionMask3,
				m_CombinedCollisionMask = collisionMask4,
				m_EdgeCompositionAreas = edgeCompositionAreas,
				m_StartCompositionAreas = startCompositionAreas,
				m_EndCompositionAreas = endCompositionAreas,
				m_Data = data,
				m_ErrorQueue = errorQueue,
				m_EditorMode = editorMode
			};
			objectSearchTree.Iterate(ref objectIterator);
		}
		AreaIterator iterator2 = new AreaIterator
		{
			m_NodeOwners = nodeOwners,
			m_EdgeEntity = entity,
			m_Bounds = bounds,
			m_IgnoreCollisions = ((temp.m_Flags & TempFlags.Delete) != 0),
			m_IgnoreProtectedAreas = ((temp.m_Flags & (TempFlags.Create | TempFlags.Delete | TempFlags.Modify | TempFlags.Replace | TempFlags.Upgrade)) == 0 || (temp.m_Flags & TempFlags.Hidden) != 0),
			m_EditorMode = editorMode,
			m_EdgeGeometryData = edgeGeometry,
			m_StartNodeGeometryData = startNodeGeometry,
			m_EndNodeGeometryData = endNodeGeometry,
			m_EdgeCompositionData = netCompositionData,
			m_StartCompositionData = netCompositionData2,
			m_EndCompositionData = netCompositionData3,
			m_EdgeCollisionMask = collisionMask,
			m_StartCollisionMask = collisionMask2,
			m_EndCollisionMask = collisionMask3,
			m_CombinedCollisionMask = collisionMask4,
			m_Data = data,
			m_ErrorQueue = errorQueue
		};
		areaSearchTree.Iterate(ref iterator2);
		if ((temp.m_Flags & TempFlags.Delete) == 0 && edgeList.Length != 0)
		{
			int num = 0;
			int num2 = edgeList.Length;
			float3 @float = edgeList[edgeList.Length - 1].m_Bounds.max - edgeList[0].m_Bounds.min;
			bool flag3 = @float.z > @float.x;
			while (num < num2)
			{
				int num3 = num + num2 >> 1;
				bool2 @bool = edgeList[num3].m_Bounds.min.xz < bounds.min.xz;
				if (flag3 ? @bool.y : @bool.x)
				{
					num = num3 + 1;
				}
				else
				{
					num2 = num3;
				}
			}
			Edge edge3 = default(Edge);
			if (data.m_Owner.TryGetComponent(edge.m_Start, out var componentData2))
			{
				edge3.m_Start = componentData2.m_Owner;
			}
			if (data.m_Owner.TryGetComponent(edge.m_End, out componentData2))
			{
				edge3.m_End = componentData2.m_Owner;
			}
			for (int j = 0; j < edgeList.Length; j++)
			{
				ValidationSystem.BoundsData boundsData = edgeList[j];
				bool2 bool2 = boundsData.m_Bounds.min.xz > bounds.max.xz;
				if (flag3 ? bool2.y : bool2.x)
				{
					break;
				}
				if ((collisionMask4 & CollisionMask.OnGround) != 0)
				{
					if (!MathUtils.Intersect(bounds.xz, boundsData.m_Bounds.xz))
					{
						continue;
					}
				}
				else if (!MathUtils.Intersect(bounds, boundsData.m_Bounds))
				{
					continue;
				}
				if (boundsData.m_Entity == entity || (boundsData.m_Bounds.min.x == bounds.min.x && boundsData.m_Entity.Index < entity.Index))
				{
					continue;
				}
				Entity entity3 = boundsData.m_Entity;
				if (data.m_Owner.TryGetComponent(boundsData.m_Entity, out var componentData3))
				{
					Entity owner4 = componentData3.m_Owner;
					if (!data.m_AssetStamp.HasComponent(owner4))
					{
						entity3 = owner4;
						while (data.m_Owner.HasComponent(entity3) && !data.m_Building.HasComponent(entity3))
						{
							owner4 = data.m_Owner[entity3].m_Owner;
							if (data.m_AssetStamp.HasComponent(owner4))
							{
								break;
							}
							entity3 = owner4;
						}
					}
					if (data.m_Edge.TryGetComponent(componentData3.m_Owner, out var componentData4) && (edge.m_Start == componentData4.m_Start || edge.m_Start == componentData4.m_End || edge.m_End == componentData4.m_Start || edge.m_End == componentData4.m_End))
					{
						continue;
					}
				}
				if (!(entity2 == entity3))
				{
					Edge edgeData = data.m_Edge[boundsData.m_Entity];
					if (!(edge.m_Start == edgeData.m_Start) && !(edge.m_Start == edgeData.m_End) && !(edge.m_End == edgeData.m_Start) && !(edge.m_End == edgeData.m_End) && (!flag2 || (!(componentData.m_Start == edgeData.m_Start) && !(componentData.m_Start == edgeData.m_End) && !(componentData.m_End == edgeData.m_Start) && !(componentData.m_End == edgeData.m_End))) && !(boundsData.m_Entity == edge3.m_Start) && !(boundsData.m_Entity == edge3.m_End) && (!data.m_Owner.TryGetComponent(edgeData.m_Start, out componentData2) || !(componentData2.m_Owner == entity)) && (!data.m_Owner.TryGetComponent(edgeData.m_End, out componentData2) || !(componentData2.m_Owner == entity)))
					{
						EdgeGeometry edgeGeometryData = data.m_EdgeGeometry[boundsData.m_Entity];
						StartNodeGeometry startNodeGeometryData = data.m_StartNodeGeometry[boundsData.m_Entity];
						EndNodeGeometry endNodeGeometryData = data.m_EndNodeGeometry[boundsData.m_Entity];
						Composition compositionData = data.m_Composition[boundsData.m_Entity];
						Temp temp2 = data.m_Temp[boundsData.m_Entity];
						iterator.CheckOverlap(entity3, boundsData.m_Entity, boundsData.m_Bounds, edgeData, compositionData, edgeGeometryData, startNodeGeometryData, endNodeGeometryData, (temp2.m_Flags & TempFlags.Essential) != 0, componentData3.m_Owner != Entity.Null);
					}
				}
			}
		}
		Bounds3 errorBounds = default(Bounds3);
		errorBounds.min = float.MaxValue;
		errorBounds.max = float.MinValue;
		bool flag4 = false;
		if ((temp.m_Flags & TempFlags.Essential) == 0)
		{
			flag4 = !data.m_NetElevation.HasComponent(entity) || !data.m_NetElevation.HasComponent(edge.m_Start) || !data.m_NetElevation.HasComponent(edge.m_End);
		}
		if ((temp.m_Flags & TempFlags.Delete) == 0)
		{
			bool num4 = entity2 != entity && IsInternal(entity2, edge.m_Start, data.m_ConnectedEdges[edge.m_Start], data);
			bool flag5 = entity2 != entity && IsInternal(entity2, edge.m_End, data.m_ConnectedEdges[edge.m_End], data);
			bool flag6 = false;
			if (!num4 || !flag5)
			{
				flag6 |= CheckGeometryShape(edgeGeometry, ref errorBounds);
			}
			if (!num4)
			{
				flag6 |= CheckGeometryShape(startNodeGeometry.m_Geometry, ref errorBounds);
			}
			if (!flag5)
			{
				flag6 |= CheckGeometryShape(endNodeGeometry.m_Geometry, ref errorBounds);
			}
			if (flag6)
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorType = ErrorType.InvalidShape,
					m_ErrorSeverity = ErrorSeverity.Error,
					m_Position = MathUtils.Center(errorBounds),
					m_TempEntity = entity
				});
			}
			if (data.m_PrefabNetGeometry.HasComponent(prefabRef.m_Prefab))
			{
				Curve curve = data.m_Curve[entity];
				NetGeometryData netGeometryData = data.m_PrefabNetGeometry[prefabRef.m_Prefab];
				Bounds1 edgeLengthRange = netGeometryData.m_EdgeLengthRange;
				if (_fixed.m_Index >= 0 && data.m_PrefabFixedElements.HasBuffer(prefabRef.m_Prefab))
				{
					DynamicBuffer<FixedNetElement> dynamicBuffer2 = data.m_PrefabFixedElements[prefabRef.m_Prefab];
					if (_fixed.m_Index < dynamicBuffer2.Length)
					{
						Bounds1 lengthRange = dynamicBuffer2[_fixed.m_Index].m_LengthRange;
						edgeLengthRange.min = math.select(lengthRange.min, lengthRange.min * 0.6f, lengthRange.max == lengthRange.min);
						edgeLengthRange.max = lengthRange.max;
					}
				}
				if ((netCompositionData.m_State & CompositionState.HalfLength) != 0)
				{
					edgeLengthRange.min *= 0.1f;
				}
				edgeLengthRange.max *= 1.1f;
				Bezier4x3 bezier4x = MathUtils.Lerp(edgeGeometry.m_Start.m_Left, edgeGeometry.m_Start.m_Right, 0.5f);
				Bezier4x3 bezier4x2 = MathUtils.Lerp(edgeGeometry.m_End.m_Left, edgeGeometry.m_End.m_Right, 0.5f);
				float num5 = MathUtils.Length(bezier4x.xz);
				float num6 = MathUtils.Length(bezier4x2.xz);
				if (num5 + num6 < edgeLengthRange.min)
				{
					errorQueue.Enqueue(new ErrorData
					{
						m_ErrorType = ErrorType.ShortDistance,
						m_ErrorSeverity = ErrorSeverity.Error,
						m_Position = math.lerp(edgeGeometry.m_Start.m_Left.d, edgeGeometry.m_Start.m_Right.d, 0.5f),
						m_TempEntity = entity
					});
				}
				if (num5 + num6 > edgeLengthRange.max)
				{
					errorQueue.Enqueue(new ErrorData
					{
						m_ErrorType = ErrorType.LongDistance,
						m_ErrorSeverity = ErrorSeverity.Error,
						m_Position = math.lerp(edgeGeometry.m_Start.m_Left.d, edgeGeometry.m_Start.m_Right.d, 0.5f),
						m_TempEntity = entity
					});
				}
				if ((netGeometryData.m_Flags & GeometryFlags.FlattenTerrain) != 0 && (temp.m_Flags & TempFlags.Essential) != 0)
				{
					flag4 = false;
				}
				if (netGeometryData.m_MaxSlopeSteepness != 0f && !flag4)
				{
					float3 float2 = default(float3);
					float2.x = math.abs(bezier4x.d.y - bezier4x.a.y) / math.max(0.1f, num5);
					float2.y = math.abs(bezier4x2.d.y - bezier4x2.a.y) / math.max(0.1f, num6);
					float2.z = math.abs(curve.m_Bezier.d.y - curve.m_Bezier.a.y) / math.max(0.1f, MathUtils.Length(curve.m_Bezier.xz));
					bool3 x = float2 >= new float3(netGeometryData.m_MaxSlopeSteepness * 2f, netGeometryData.m_MaxSlopeSteepness * 2f, netGeometryData.m_MaxSlopeSteepness + 0.0005f);
					if (math.any(x))
					{
						float4 float3 = default(float4);
						if (x.x)
						{
							float3 += new float4(math.lerp(MathUtils.Position(edgeGeometry.m_Start.m_Left, 0.5f), MathUtils.Position(edgeGeometry.m_Start.m_Right, 0.5f), 0.5f), 1f);
						}
						if (x.y)
						{
							float3 += new float4(math.lerp(MathUtils.Position(edgeGeometry.m_End.m_Left, 0.5f), MathUtils.Position(edgeGeometry.m_End.m_Right, 0.5f), 0.5f), 1f);
						}
						if (x.z)
						{
							float3 += new float4(math.lerp(edgeGeometry.m_Start.m_Left.d, edgeGeometry.m_Start.m_Right.d, 0.5f), 1f);
						}
						errorQueue.Enqueue(new ErrorData
						{
							m_ErrorType = ErrorType.SteepSlope,
							m_ErrorSeverity = ErrorSeverity.Error,
							m_Position = float3.xyz / float3.w,
							m_TempEntity = entity
						});
					}
				}
				if ((netGeometryData.m_Flags & GeometryFlags.RequireElevated) != 0)
				{
					data.m_NetElevation.TryGetComponent(edge.m_Start, out var componentData5);
					data.m_NetElevation.TryGetComponent(entity, out var componentData6);
					data.m_NetElevation.TryGetComponent(edge.m_End, out var componentData7);
					if (!math.all(math.max(math.max(math.cmin(componentData5.m_Elevation), math.cmin(componentData7.m_Elevation)), componentData6.m_Elevation) >= netGeometryData.m_ElevationLimit * 2f))
					{
						errorQueue.Enqueue(new ErrorData
						{
							m_ErrorType = ErrorType.LowElevation,
							m_ErrorSeverity = ErrorSeverity.Error,
							m_Position = math.lerp(edgeGeometry.m_Start.m_Left.d, edgeGeometry.m_Start.m_Right.d, 0.5f),
							m_TempEntity = entity
						});
					}
				}
			}
		}
		if ((temp.m_Flags & (TempFlags.Create | TempFlags.Modify)) != 0 && !flag4 && data.m_PlaceableNet.HasComponent(prefabRef.m_Prefab))
		{
			PlaceableNetData placeableNetData = data.m_PlaceableNet[prefabRef.m_Prefab];
			errorBounds.min = float.MaxValue;
			errorBounds.max = float.MinValue;
			if (CheckSurface(waterSurfaceData, terrainHeightData, placeableNetData, netCompositionData, edgeGeometry.m_Start, ref errorBounds) | CheckSurface(waterSurfaceData, terrainHeightData, placeableNetData, netCompositionData, edgeGeometry.m_End, ref errorBounds) | CheckSurface(waterSurfaceData, terrainHeightData, placeableNetData, netCompositionData2, startNodeGeometry.m_Geometry.m_Left, ref errorBounds) | CheckSurface(waterSurfaceData, terrainHeightData, placeableNetData, netCompositionData2, startNodeGeometry.m_Geometry.m_Right, ref errorBounds) | CheckSurface(waterSurfaceData, terrainHeightData, placeableNetData, netCompositionData3, endNodeGeometry.m_Geometry.m_Left, ref errorBounds) | CheckSurface(waterSurfaceData, terrainHeightData, placeableNetData, netCompositionData3, endNodeGeometry.m_Geometry.m_Right, ref errorBounds))
			{
				ErrorData value2 = default(ErrorData);
				if ((placeableNetData.m_PlacementFlags & PlacementFlags.Floating) != PlacementFlags.None)
				{
					value2.m_ErrorType = ErrorType.NoWater;
				}
				else
				{
					value2.m_ErrorType = ErrorType.InWater;
				}
				value2.m_ErrorSeverity = ErrorSeverity.Error;
				value2.m_Position = MathUtils.Center(errorBounds);
				value2.m_TempEntity = entity;
				errorQueue.Enqueue(value2);
			}
		}
		if ((temp.m_Flags & (TempFlags.Create | TempFlags.Modify | TempFlags.Replace | TempFlags.Upgrade)) != 0)
		{
			bounds = edgeGeometry.m_Bounds;
			if (math.any(startNodeGeometry.m_Geometry.m_Left.m_Length > 0.05f) | math.any(startNodeGeometry.m_Geometry.m_Right.m_Length > 0.05f))
			{
				bounds |= startNodeGeometry.m_Geometry.m_Bounds;
			}
			if (math.any(endNodeGeometry.m_Geometry.m_Left.m_Length > 0.05f) | math.any(endNodeGeometry.m_Geometry.m_Right.m_Length > 0.05f))
			{
				bounds |= endNodeGeometry.m_Geometry.m_Bounds;
			}
			Game.Objects.ValidationHelpers.ValidateWorldBounds(entity, owner, bounds, data, terrainHeightData, errorQueue);
		}
	}
```

- `public static ValidateLane(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Net.Lane lane, Game.Net.TrackLane trackLane, Game.Net.Curve curve, Game.Net.EdgeLane edgeLane, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateLane(Entity entity, Owner owner, Lane lane, TrackLane trackLane, Curve curve, EdgeLane edgeLane, PrefabRef prefabRef, ValidationSystem.EntityData data, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		if (data.m_Edge.HasComponent(owner.m_Owner))
		{
			TrackLaneData trackLaneData = data.m_TrackLaneData[prefabRef.m_Prefab];
			if (trackLane.m_Curviness > trackLaneData.m_MaxCurviness && data.m_Temp.TryGetComponent(owner.m_Owner, out var componentData) && (componentData.m_Flags & TempFlags.Essential) != 0)
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorType = ErrorType.TightCurve,
					m_Position = MathUtils.Position(curve.m_Bezier, 0.5f),
					m_ErrorSeverity = ErrorSeverity.Error,
					m_TempEntity = owner.m_Owner
				});
			}
			Edge edge = data.m_Edge[owner.m_Owner];
			bool flag = (trackLane.m_Flags & TrackLaneFlags.Twoway) != 0;
			bool flag2;
			Entity entity2;
			if (edgeLane.m_EdgeDelta.x < 0.001f)
			{
				flag2 = FindConnectedLane(edge.m_Start, owner.m_Owner, lane.m_StartNode, data) || IsIgnored(owner.m_Owner, edge.m_Start, data, trackLaneData.m_TrackTypes, flag, isTarget: true);
				entity2 = edge.m_Start;
			}
			else if (edgeLane.m_EdgeDelta.x > 0.999f)
			{
				flag2 = FindConnectedLane(edge.m_End, owner.m_Owner, lane.m_StartNode, data) || IsIgnored(owner.m_Owner, edge.m_End, data, trackLaneData.m_TrackTypes, flag, isTarget: true);
				entity2 = edge.m_End;
			}
			else
			{
				flag2 = true;
				entity2 = Entity.Null;
			}
			bool flag3;
			Entity entity3;
			if (edgeLane.m_EdgeDelta.y < 0.001f)
			{
				flag3 = FindConnectedLane(edge.m_Start, owner.m_Owner, lane.m_EndNode, data) || IsIgnored(owner.m_Owner, edge.m_Start, data, trackLaneData.m_TrackTypes, isSource: true, flag);
				entity3 = edge.m_Start;
			}
			else if (edgeLane.m_EdgeDelta.y > 0.999f)
			{
				flag3 = FindConnectedLane(edge.m_End, owner.m_Owner, lane.m_EndNode, data) || IsIgnored(owner.m_Owner, edge.m_End, data, trackLaneData.m_TrackTypes, isSource: true, flag);
				entity3 = edge.m_End;
			}
			else
			{
				flag3 = true;
				entity3 = Entity.Null;
			}
			if (!flag2 && data.m_Temp.TryGetComponent(entity2, out var componentData2) && (componentData2.m_Flags & TempFlags.Essential) != 0)
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorType = ErrorType.TightCurve,
					m_Position = (curve.m_Bezier.a + data.m_Node[entity2].m_Position) * 0.5f,
					m_ErrorSeverity = ErrorSeverity.Warning,
					m_TempEntity = entity2
				});
			}
			if (!flag3 && data.m_Temp.TryGetComponent(entity3, out var componentData3) && (componentData3.m_Flags & TempFlags.Essential) != 0)
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorType = ErrorType.TightCurve,
					m_Position = (curve.m_Bezier.d + data.m_Node[entity3].m_Position) * 0.5f,
					m_ErrorSeverity = ErrorSeverity.Warning,
					m_TempEntity = entity3
				});
			}
		}
	}
```


## Nested types

- `Game.Net.ValidationHelpers+NetIterator`  
- `Game.Net.ValidationHelpers+ObjectIterator`  
- `Game.Net.ValidationHelpers+AreaIterator`  

