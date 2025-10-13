# Game.Net.NetUtils

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NetUtils
{
    public static const System.Single DEFAULT_ELEVATION_STEP;
    public static const System.Single MAX_LANE_WEAR;
    public static const System.Single MAX_LOCAL_CONNECT_DISTANCE;
    public static const System.Single MAX_LOCAL_CONNECT_HEIGHT;
    public static const System.Single MAX_SNAP_HEIGHT;
    public static const System.Single UTURN_LIMIT_COS;
    public static const System.Single TURN_LIMIT_COS;
    public static const System.Single GENTLETURN_LIMIT_COS;
    public static const System.Single MAX_PASSING_CURVINESS_STREET;
    public static const System.Single MAX_PASSING_CURVINESS_HIGHWAY;
    public static const System.Single MIN_VISIBLE_EDGE_LENGTH;
    public static const System.Single MIN_VISIBLE_NODE_LENGTH;
    public static const System.Single MIN_VISIBLE_LANE_LENGTH;

    public static System.Void AddLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition);
    public static Game.Net.Node AdjustPosition(Game.Net.Node node, Game.Simulation.TerrainHeightData& terrainHeightData);
    public static Game.Net.Node AdjustPosition(Game.Net.Node node, Game.Buildings.BuildingUtils+LotInfo& lotInfo);
    public static Game.Net.Curve AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData);
    public static Game.Net.Curve AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData);
    public static Game.Net.Curve AdjustPosition(Game.Net.Curve curve, Unity.Mathematics.bool2 fixedStart, System.Boolean linearMiddle, Unity.Mathematics.bool2 fixedEnd, Game.Buildings.BuildingUtils+LotInfo& lotInfo);
    public static System.Single CalculateCurviness(Game.Net.Curve curve, System.Single width);
    public static System.Single CalculateCurviness(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 position2, Unity.Mathematics.float3 tangent2);
    public static System.Single CalculateCurviness(Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 tangent2, System.Single distance);
    public static System.Single CalculateEndCurviness(Game.Net.Curve curve, System.Single width);
    public static System.Single CalculateStartCurviness(Game.Net.Curve curve, System.Single width);
    public static System.Boolean CanConnect(Game.Prefabs.NetData netData1, Game.Prefabs.NetData netData2);
    public static System.Int32 ChooseClosestLane(System.Int32 minIndex, System.Int32 maxIndex, Unity.Mathematics.float3 comparePosition, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, System.Single curvePosition);
    public static Colossal.Mathematics.Bezier4x3 CircleCurve(Unity.Mathematics.float3 center, System.Single xOffset, System.Single zOffset);
    public static Colossal.Mathematics.Bezier4x3 CircleCurve(Unity.Mathematics.float3 center, Unity.Mathematics.quaternion rotation, System.Single xOffset, System.Single zOffset);
    public static System.Single ExtendedClampLength(Colossal.Mathematics.Bezier4x2 curve, System.Single distance);
    public static System.Single ExtendedDistance(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 position, System.Single& t);
    public static System.Single ExtendedLength(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
    public static System.Void ExtendedPositionAndTangent(Colossal.Mathematics.Bezier4x3 curve, System.Single t, Unity.Mathematics.float3& position, Unity.Mathematics.float3& tangent);
    public static System.Boolean FindConnectedLane(Unity.Entities.Entity& laneEntity, System.Boolean& forward, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
    public static System.Boolean FindEdgeLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, System.Boolean startNode);
    public static System.Single FindMiddleTangentPos(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 offset);
    public static System.Boolean FindNextLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
    public static System.Boolean FindPrevLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
    public static Colossal.Mathematics.Bezier4x3 FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 middlePos, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos);
    public static Colossal.Mathematics.Bezier4x3 FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos);
    public static Colossal.Mathematics.Bezier4x3 FitCurve(Colossal.Mathematics.Line3+Segment startLine, Colossal.Mathematics.Line3+Segment endLine);
    public static System.Void FlipUpgradeTrafficHandedness(Game.Prefabs.CompositionFlags& flags);
    public static System.Single GetAvailability(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Game.Net.AvailableResource resource, System.Single curvePos);
    public static Game.Common.CollisionMask GetCollisionMask(Game.Prefabs.NetCompositionData compositionData, System.Boolean ignoreMarkers);
    public static Game.Common.CollisionMask GetCollisionMask(Game.Net.LabelPosition labelPosition);
    public static System.Int32 GetConstructionCost(Game.Net.Curve curve, Game.Net.Elevation startElevation, Game.Net.Elevation endElevation, Game.Prefabs.PlaceableNetComposition placeableNetData);
    public static Unity.Mathematics.quaternion GetNodeRotation(Unity.Mathematics.float3 tangent);
    public static Unity.Mathematics.quaternion GetNodeRotation(Unity.Mathematics.float3 tangent, Unity.Mathematics.quaternion defaultRotation);
    public static System.Int32 GetParkingSlotCount(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane);
    public static System.Single GetParkingSlotInterval(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane, System.Int32 slotCount);
    private static System.Single GetParkingSlotSpace(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane);
    public static System.Int32 GetRefundAmount(Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData);
    public static System.Single GetServiceCoverage(Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> coverages, Game.Net.CoverageService service, System.Single curvePos);
    public static Game.Prefabs.SubNet GetSubNet(Unity.Entities.DynamicBuffer<Game.Prefabs.SubNet> subNets, System.Int32 index, System.Boolean lefthandTraffic, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryLookup);
    public static System.Single GetTerrainSmoothingWidth(Game.Prefabs.NetData netData);
    public static Unity.Mathematics.float4 GetTrafficFlowSpeed(Game.Net.Road road);
    public static Unity.Mathematics.float4 GetTrafficFlowSpeed(Unity.Mathematics.float4 duration, Unity.Mathematics.float4 distance);
    public static System.Single GetTrafficFlowSpeed(System.Single duration, System.Single distance);
    public static System.Int32 GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost);
    public static System.Int32 GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData);
    public static System.Int32 GetUpkeepCost(Game.Net.Curve curve, Game.Prefabs.PlaceableNetComposition placeableNetData);
    public static System.Boolean IsTurn(Unity.Mathematics.float2 startPosition, Unity.Mathematics.float2 startDirection, Unity.Mathematics.float2 endPosition, Unity.Mathematics.float2 endDirection, System.Boolean& right, System.Boolean& gentle, System.Boolean& uturn);
    public static Colossal.Mathematics.Bezier4x3 OffsetCurveLeftSmooth(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 offset);
    public static System.Void RemoveLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject);
    public static System.Boolean ShouldInvert(Game.Prefabs.NetInvertMode invertMode, System.Boolean lefthandTraffic);
    public static Colossal.Mathematics.Bezier4x3 StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos);
    public static Colossal.Mathematics.Bezier4x3 StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, System.Single hanging);
    public static System.Boolean TryGetCombinedSegmentForLanes(Game.Net.EdgeGeometry edgeGeometry, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Net.Segment& segment);
    public static System.Void UpdateLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition);
}
```


## Fields

- `public static const System.Single DEFAULT_ELEVATION_STEP`  

```csharp
public static const System.Single DEFAULT_ELEVATION_STEP;
```

- `public static const System.Single MAX_LANE_WEAR`  

```csharp
public static const System.Single MAX_LANE_WEAR;
```

- `public static const System.Single MAX_LOCAL_CONNECT_DISTANCE`  

```csharp
public static const System.Single MAX_LOCAL_CONNECT_DISTANCE;
```

- `public static const System.Single MAX_LOCAL_CONNECT_HEIGHT`  

```csharp
public static const System.Single MAX_LOCAL_CONNECT_HEIGHT;
```

- `public static const System.Single MAX_SNAP_HEIGHT`  

```csharp
public static const System.Single MAX_SNAP_HEIGHT;
```

- `public static const System.Single UTURN_LIMIT_COS`  

```csharp
public static const System.Single UTURN_LIMIT_COS;
```

- `public static const System.Single TURN_LIMIT_COS`  

```csharp
public static const System.Single TURN_LIMIT_COS;
```

- `public static const System.Single GENTLETURN_LIMIT_COS`  

```csharp
public static const System.Single GENTLETURN_LIMIT_COS;
```

- `public static const System.Single MAX_PASSING_CURVINESS_STREET`  

```csharp
public static const System.Single MAX_PASSING_CURVINESS_STREET;
```

- `public static const System.Single MAX_PASSING_CURVINESS_HIGHWAY`  

```csharp
public static const System.Single MAX_PASSING_CURVINESS_HIGHWAY;
```

- `public static const System.Single MIN_VISIBLE_EDGE_LENGTH`  

```csharp
public static const System.Single MIN_VISIBLE_EDGE_LENGTH;
```

- `public static const System.Single MIN_VISIBLE_NODE_LENGTH`  

```csharp
public static const System.Single MIN_VISIBLE_NODE_LENGTH;
```

- `public static const System.Single MIN_VISIBLE_LANE_LENGTH`  

```csharp
public static const System.Single MIN_VISIBLE_LANE_LENGTH;
```


## Methods

- `public static AddLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition) : System.Void`  

```csharp
public static void AddLaneObject(DynamicBuffer<LaneObject> buffer, Entity laneObject, float2 curvePosition)
	{
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i].m_CurvePosition.y >= curvePosition.y)
			{
				buffer.Insert(i, new LaneObject(laneObject, curvePosition));
				return;
			}
		}
		buffer.Add(new LaneObject(laneObject, curvePosition));
	}
```

- `public static AdjustPosition(Game.Net.Node node, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Net.Node`  

```csharp
public static Curve AdjustPosition(Curve curve, bool2 fixedStart, bool linearMiddle, bool2 fixedEnd, ref BuildingUtils.LotInfo lotInfo)
	{
		Curve result = curve;
		if (!fixedStart.x)
		{
			result.m_Bezier.a.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.a);
		}
		if (!fixedEnd.x)
		{
			result.m_Bezier.d.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.d);
		}
		if (linearMiddle)
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 1f / 3f);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 2f / 3f);
			}
		}
		else
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.b);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.c);
			}
			float num = result.m_Bezier.b.y - MathUtils.Position(result.m_Bezier.y, 1f / 3f);
			float num2 = result.m_Bezier.c.y - MathUtils.Position(result.m_Bezier.y, 2f / 3f);
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y += num * 3f - num2 * 1.5f;
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y += num2 * 3f - num * 1.5f;
			}
		}
		return result;
	}
```

- `public static AdjustPosition(Game.Net.Node node, Game.Buildings.BuildingUtils+LotInfo& lotInfo) : Game.Net.Node`  

```csharp
public static Curve AdjustPosition(Curve curve, bool2 fixedStart, bool linearMiddle, bool2 fixedEnd, ref BuildingUtils.LotInfo lotInfo)
	{
		Curve result = curve;
		if (!fixedStart.x)
		{
			result.m_Bezier.a.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.a);
		}
		if (!fixedEnd.x)
		{
			result.m_Bezier.d.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.d);
		}
		if (linearMiddle)
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 1f / 3f);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 2f / 3f);
			}
		}
		else
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.b);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.c);
			}
			float num = result.m_Bezier.b.y - MathUtils.Position(result.m_Bezier.y, 1f / 3f);
			float num2 = result.m_Bezier.c.y - MathUtils.Position(result.m_Bezier.y, 2f / 3f);
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y += num * 3f - num2 * 1.5f;
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y += num2 * 3f - num * 1.5f;
			}
		}
		return result;
	}
```

- `public static AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Net.Curve`  

```csharp
public static Curve AdjustPosition(Curve curve, bool2 fixedStart, bool linearMiddle, bool2 fixedEnd, ref BuildingUtils.LotInfo lotInfo)
	{
		Curve result = curve;
		if (!fixedStart.x)
		{
			result.m_Bezier.a.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.a);
		}
		if (!fixedEnd.x)
		{
			result.m_Bezier.d.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.d);
		}
		if (linearMiddle)
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 1f / 3f);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 2f / 3f);
			}
		}
		else
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.b);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.c);
			}
			float num = result.m_Bezier.b.y - MathUtils.Position(result.m_Bezier.y, 1f / 3f);
			float num2 = result.m_Bezier.c.y - MathUtils.Position(result.m_Bezier.y, 2f / 3f);
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y += num * 3f - num2 * 1.5f;
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y += num2 * 3f - num * 1.5f;
			}
		}
		return result;
	}
```

- `public static AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData) : Game.Net.Curve`  

```csharp
public static Curve AdjustPosition(Curve curve, bool2 fixedStart, bool linearMiddle, bool2 fixedEnd, ref BuildingUtils.LotInfo lotInfo)
	{
		Curve result = curve;
		if (!fixedStart.x)
		{
			result.m_Bezier.a.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.a);
		}
		if (!fixedEnd.x)
		{
			result.m_Bezier.d.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.d);
		}
		if (linearMiddle)
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 1f / 3f);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 2f / 3f);
			}
		}
		else
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.b);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.c);
			}
			float num = result.m_Bezier.b.y - MathUtils.Position(result.m_Bezier.y, 1f / 3f);
			float num2 = result.m_Bezier.c.y - MathUtils.Position(result.m_Bezier.y, 2f / 3f);
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y += num * 3f - num2 * 1.5f;
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y += num2 * 3f - num * 1.5f;
			}
		}
		return result;
	}
```

- `public static AdjustPosition(Game.Net.Curve curve, Unity.Mathematics.bool2 fixedStart, System.Boolean linearMiddle, Unity.Mathematics.bool2 fixedEnd, Game.Buildings.BuildingUtils+LotInfo& lotInfo) : Game.Net.Curve`  

```csharp
public static Curve AdjustPosition(Curve curve, bool2 fixedStart, bool linearMiddle, bool2 fixedEnd, ref BuildingUtils.LotInfo lotInfo)
	{
		Curve result = curve;
		if (!fixedStart.x)
		{
			result.m_Bezier.a.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.a);
		}
		if (!fixedEnd.x)
		{
			result.m_Bezier.d.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.d);
		}
		if (linearMiddle)
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 1f / 3f);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = math.lerp(result.m_Bezier.a.y, result.m_Bezier.d.y, 2f / 3f);
			}
		}
		else
		{
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.b);
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y = BuildingUtils.SampleHeight(ref lotInfo, curve.m_Bezier.c);
			}
			float num = result.m_Bezier.b.y - MathUtils.Position(result.m_Bezier.y, 1f / 3f);
			float num2 = result.m_Bezier.c.y - MathUtils.Position(result.m_Bezier.y, 2f / 3f);
			if (!fixedStart.y)
			{
				result.m_Bezier.b.y += num * 3f - num2 * 1.5f;
			}
			if (!fixedEnd.y)
			{
				result.m_Bezier.c.y += num2 * 3f - num * 1.5f;
			}
		}
		return result;
	}
```

- `public static CalculateCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  

```csharp
public static float CalculateCurviness(float3 tangent1, float3 tangent2, float distance)
	{
		float num = math.acos(math.clamp(math.dot(tangent1, tangent2), -1f, 1f));
		return 2f * math.sin(num * 0.5f) / distance;
	}
```

- `public static CalculateCurviness(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 position2, Unity.Mathematics.float3 tangent2) : System.Single`  

```csharp
public static float CalculateCurviness(float3 tangent1, float3 tangent2, float distance)
	{
		float num = math.acos(math.clamp(math.dot(tangent1, tangent2), -1f, 1f));
		return 2f * math.sin(num * 0.5f) / distance;
	}
```

- `public static CalculateCurviness(Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 tangent2, System.Single distance) : System.Single`  

```csharp
public static float CalculateCurviness(float3 tangent1, float3 tangent2, float distance)
	{
		float num = math.acos(math.clamp(math.dot(tangent1, tangent2), -1f, 1f));
		return 2f * math.sin(num * 0.5f) / distance;
	}
```

- `public static CalculateEndCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  

```csharp
public static float CalculateEndCurviness(Curve curve, float width)
	{
		if (curve.m_Length > 0.1f)
		{
			float3 tangent = MathUtils.Tangent(curve.m_Bezier, 0.5f);
			float3 position = MathUtils.Position(curve.m_Bezier, 0.5f);
			float3 @float = MathUtils.Tangent(curve.m_Bezier, 0.75f);
			float3 float2 = MathUtils.Position(curve.m_Bezier, 0.75f);
			float3 tangent2 = MathUtils.EndTangent(curve.m_Bezier);
			float3 d = curve.m_Bezier.d;
			float2 x = default(float2);
			x.x = CalculateCurviness(position, tangent, float2, @float);
			x.y = CalculateCurviness(float2, @float, d, tangent2);
			return math.cmax(x);
		}
		return 0f;
	}
```

- `public static CalculateStartCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  

```csharp
public static float CalculateStartCurviness(Curve curve, float width)
	{
		if (curve.m_Length > 0.1f)
		{
			float3 tangent = MathUtils.StartTangent(curve.m_Bezier);
			float3 a = curve.m_Bezier.a;
			float3 @float = MathUtils.Tangent(curve.m_Bezier, 0.25f);
			float3 float2 = MathUtils.Position(curve.m_Bezier, 0.25f);
			float3 tangent2 = MathUtils.Tangent(curve.m_Bezier, 0.5f);
			float3 position = MathUtils.Position(curve.m_Bezier, 0.5f);
			float2 x = default(float2);
			x.x = CalculateCurviness(a, tangent, float2, @float);
			x.y = CalculateCurviness(float2, @float, position, tangent2);
			return math.cmax(x);
		}
		return 0f;
	}
```

- `public static CanConnect(Game.Prefabs.NetData netData1, Game.Prefabs.NetData netData2) : System.Boolean`  

```csharp
public static bool CanConnect(NetData netData1, NetData netData2)
	{
		if ((netData1.m_RequiredLayers & netData2.m_ConnectLayers) != netData1.m_RequiredLayers)
		{
			return (netData2.m_RequiredLayers & netData1.m_ConnectLayers) == netData2.m_RequiredLayers;
		}
		return true;
	}
```

- `public static ChooseClosestLane(System.Int32 minIndex, System.Int32 maxIndex, Unity.Mathematics.float3 comparePosition, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, System.Single curvePosition) : System.Int32`  

```csharp
public static int ChooseClosestLane(int minIndex, int maxIndex, float3 comparePosition, DynamicBuffer<SubLane> lanes, ComponentLookup<Curve> curves, float curvePosition)
	{
		float num = float.MaxValue;
		int result = minIndex;
		maxIndex = math.min(maxIndex, lanes.Length - 1);
		for (int i = minIndex; i <= maxIndex; i++)
		{
			Entity subLane = lanes[i].m_SubLane;
			float t;
			float num2 = MathUtils.DistanceSquared(curves[subLane].m_Bezier, comparePosition, out t);
			if (num2 < num)
			{
				num = num2;
				result = i;
			}
		}
		return result;
	}
```

- `public static CircleCurve(Unity.Mathematics.float3 center, System.Single xOffset, System.Single zOffset) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Bezier4x3 CircleCurve(float3 center, quaternion rotation, float xOffset, float zOffset)
	{
		float2 xz = math.forward(rotation).xz;
		float2 @float = MathUtils.Right(xz);
		Bezier4x3 result = new Bezier4x3(center, center, center, center);
		result.a.xz += @float * xOffset;
		result.b.xz += @float * xOffset;
		result.b.xz += xz * (zOffset * 0.5522848f);
		result.c.xz += @float * (xOffset * 0.5522848f);
		result.c.xz += xz * zOffset;
		result.d.xz += xz * zOffset;
		return result;
	}
```

- `public static CircleCurve(Unity.Mathematics.float3 center, Unity.Mathematics.quaternion rotation, System.Single xOffset, System.Single zOffset) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Bezier4x3 CircleCurve(float3 center, quaternion rotation, float xOffset, float zOffset)
	{
		float2 xz = math.forward(rotation).xz;
		float2 @float = MathUtils.Right(xz);
		Bezier4x3 result = new Bezier4x3(center, center, center, center);
		result.a.xz += @float * xOffset;
		result.b.xz += @float * xOffset;
		result.b.xz += xz * (zOffset * 0.5522848f);
		result.c.xz += @float * (xOffset * 0.5522848f);
		result.c.xz += xz * zOffset;
		result.d.xz += xz * zOffset;
		return result;
	}
```

- `public static ExtendedClampLength(Colossal.Mathematics.Bezier4x2 curve, System.Single distance) : System.Single`  

```csharp
public static float ExtendedClampLength(Bezier4x2 curve, float distance)
	{
		if (distance <= 0f)
		{
			float num = math.distance(curve.a, curve.b);
			return math.select(distance / num, 0f, num == 0f);
		}
		Bounds1 t = new Bounds1(0f, 1f);
		if (MathUtils.ClampLength(curve, ref t, distance))
		{
			return t.max;
		}
		distance -= MathUtils.Length(curve);
		float num2 = math.distance(curve.c, curve.d);
		return math.select(1f + distance / num2, 1f, num2 == 0f);
	}
```

- `public static ExtendedDistance(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 position, System.Single& t) : System.Single`  

```csharp
public static float ExtendedDistance(Bezier4x2 curve, float2 position, out float t)
	{
		float t2;
		float num = MathUtils.Distance(new Line2(curve.a, curve.a * 2f - curve.b), position, out t2);
		float t3;
		float num2 = MathUtils.Distance(curve, position, out t3);
		float t4;
		float num3 = MathUtils.Distance(new Line2(curve.d, curve.d * 2f - curve.c), position, out t4);
		if (t2 >= 0f && num < num2 && (num < num3 || t4 < 0f))
		{
			t = 0f - t2;
			return num;
		}
		if (t4 >= 0f && num3 < num2)
		{
			t = 1f + t4;
			return num3;
		}
		t = t3;
		return num2;
	}
```

- `public static ExtendedLength(Colossal.Mathematics.Bezier4x2 curve, System.Single t) : System.Single`  

```csharp
public static float ExtendedLength(Bezier4x2 curve, float t)
	{
		if (t <= 0f)
		{
			return math.distance(curve.a, curve.b) * t;
		}
		if (t <= 1f)
		{
			return MathUtils.Length(curve, new Bounds1(0f, t));
		}
		return MathUtils.Length(curve) + math.distance(curve.c, curve.d) * (t - 1f);
	}
```

- `public static ExtendedPositionAndTangent(Colossal.Mathematics.Bezier4x3 curve, System.Single t, Unity.Mathematics.float3& position, Unity.Mathematics.float3& tangent) : System.Void`  

```csharp
public static void ExtendedPositionAndTangent(Bezier4x3 curve, float t, out float3 position, out float3 tangent)
	{
		if (t <= 0f)
		{
			position = MathUtils.Position(new Line3(curve.a, curve.a * 2f - curve.b), 0f - t);
			tangent = curve.b - curve.a;
		}
		else if (t <= 1f)
		{
			position = MathUtils.Position(curve, t);
			tangent = MathUtils.Tangent(curve, t);
		}
		else
		{
			position = MathUtils.Position(new Line3(curve.d, curve.d * 2f - curve.c), t - 1f);
			tangent = curve.d - curve.c;
		}
	}
```

- `public static FindConnectedLane(Unity.Entities.Entity& laneEntity, System.Boolean& forward, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  

```csharp
public static bool FindConnectedLane(ref Entity laneEntity, ref bool forward, ref ComponentLookup<Lane> laneData, ref ComponentLookup<EdgeLane> edgeLaneData, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Edge> edgeData, ref BufferLookup<ConnectedEdge> connectedEdges, ref BufferLookup<SubLane> subLanes)
	{
		Lane lane = laneData[laneEntity];
		Entity entity = ownerData[laneEntity].m_Owner;
		Entity entity2 = entity;
		PathNode other = (forward ? lane.m_EndNode : lane.m_StartNode);
		if (edgeLaneData.HasComponent(laneEntity))
		{
			EdgeLane edgeLane = edgeLaneData[laneEntity];
			float num = (forward ? edgeLane.m_EdgeDelta.y : edgeLane.m_EdgeDelta.x);
			if (num == 0f)
			{
				entity = edgeData[entity].m_Start;
			}
			else if (num == 1f)
			{
				entity = edgeData[entity].m_End;
			}
			DynamicBuffer<SubLane> dynamicBuffer = subLanes[entity];
			for (int i = 0; i < dynamicBuffer.Length; i++)
			{
				Entity subLane = dynamicBuffer[i].m_SubLane;
				if (!(subLane == laneEntity))
				{
					Lane lane2 = laneData[subLane];
					if (lane2.m_StartNode.Equals(other))
					{
						laneEntity = subLane;
						forward = true;
						return true;
					}
					if (lane2.m_EndNode.Equals(other))
					{
						laneEntity = subLane;
						forward = false;
						return true;
					}
				}
			}
			if (entity == entity2 || !other.OwnerEquals(new PathNode(entity, 0)))
			{
				return false;
			}
		}
		if (connectedEdges.TryGetBuffer(entity, out var bufferData))
		{
			for (int j = 0; j < bufferData.Length; j++)
			{
				entity = bufferData[j].m_Edge;
				if (entity == entity2)
				{
					continue;
				}
				DynamicBuffer<SubLane> dynamicBuffer2 = subLanes[entity];
				for (int k = 0; k < dynamicBuffer2.Length; k++)
				{
					Entity subLane2 = dynamicBuffer2[k].m_SubLane;
					if (!(subLane2 == laneEntity))
					{
						Lane lane3 = laneData[subLane2];
						if (lane3.m_StartNode.Equals(other))
						{
							laneEntity = subLane2;
							forward = true;
							return true;
						}
						if (lane3.m_EndNode.Equals(other))
						{
							laneEntity = subLane2;
							forward = false;
							return true;
						}
					}
				}
			}
		}
		return false;
	}
```

- `public static FindEdgeLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, System.Boolean startNode) : System.Boolean`  

```csharp
public static bool FindEdgeLane(ref Entity entity, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Lane> laneData, ref BufferLookup<SubLane> subLanes, bool startNode)
	{
		if (!ownerData.TryGetComponent(entity, out var componentData) || !laneData.TryGetComponent(entity, out var componentData2))
		{
			return false;
		}
		if (!subLanes.TryGetBuffer(componentData.m_Owner, out var bufferData))
		{
			return false;
		}
		PathNode pathNode = (startNode ? componentData2.m_StartNode : componentData2.m_EndNode);
		for (int i = 0; i < bufferData.Length; i++)
		{
			Entity subLane = bufferData[i].m_SubLane;
			if (pathNode.EqualsIgnoreCurvePos(laneData[subLane].m_MiddleNode))
			{
				entity = subLane;
				return true;
			}
		}
		return false;
	}
```

- `public static FindMiddleTangentPos(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 offset) : System.Single`  

```csharp
public static float FindMiddleTangentPos(Bezier4x2 curve, float2 offset)
	{
		float num = math.lerp(offset.x, offset.y, 0.5f);
		float num2 = num;
		float2 value = MathUtils.Tangent(curve, offset.x);
		float2 value2 = MathUtils.Tangent(curve, offset.y);
		if (!MathUtils.TryNormalize(ref value) || !MathUtils.TryNormalize(ref value2))
		{
			return num;
		}
		float2 @float = offset;
		for (int i = 0; i < 24; i++)
		{
			float2 value3 = MathUtils.Tangent(curve, num2);
			if (!MathUtils.TryNormalize(ref value3))
			{
				break;
			}
			float num3 = math.distancesq(value, value3);
			float num4 = math.distancesq(value2, value3);
			if (num3 < num4)
			{
				@float.x = num2;
			}
			else
			{
				if (!(num3 > num4))
				{
					break;
				}
				@float.y = num2;
			}
			num2 = math.lerp(@float.x, @float.y, 0.5f);
		}
		return math.lerp(num2, num, math.saturate(0.5f + math.dot(value, value2) * 0.5f));
	}
```

- `public static FindNextLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  

```csharp
public static bool FindNextLane(ref Entity entity, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Lane> laneData, ref BufferLookup<SubLane> subLanes)
	{
		if (!ownerData.TryGetComponent(entity, out var componentData) || !laneData.TryGetComponent(entity, out var componentData2))
		{
			return false;
		}
		if (!subLanes.TryGetBuffer(componentData.m_Owner, out var bufferData))
		{
			return false;
		}
		for (int i = 0; i < bufferData.Length; i++)
		{
			Entity subLane = bufferData[i].m_SubLane;
			Lane lane = laneData[subLane];
			if (componentData2.m_EndNode.Equals(lane.m_StartNode))
			{
				entity = subLane;
				return true;
			}
		}
		return false;
	}
```

- `public static FindPrevLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  

```csharp
public static bool FindPrevLane(ref Entity entity, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Lane> laneData, ref BufferLookup<SubLane> subLanes)
	{
		if (!ownerData.TryGetComponent(entity, out var componentData) || !laneData.TryGetComponent(entity, out var componentData2))
		{
			return false;
		}
		if (!subLanes.TryGetBuffer(componentData.m_Owner, out var bufferData))
		{
			return false;
		}
		for (int i = 0; i < bufferData.Length; i++)
		{
			Entity subLane = bufferData[i].m_SubLane;
			Lane lane = laneData[subLane];
			if (componentData2.m_StartNode.Equals(lane.m_EndNode))
			{
				entity = subLane;
				return true;
			}
		}
		return false;
	}
```

- `public static FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 middlePos, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Bezier4x3 FitCurve(Line3.Segment startLine, Line3.Segment endLine)
	{
		float3 @float = MathUtils.Tangent(startLine);
		float3 float2 = MathUtils.Tangent(endLine);
		float num = math.length(@float.xz);
		float num2 = math.length(float2.xz);
		if (num != 0f)
		{
			@float /= num;
		}
		else
		{
			@float.xz = endLine.b.xz - startLine.a.xz;
			num = math.length(@float.xz);
			if (num != 0f)
			{
				@float /= num;
			}
		}
		if (num2 != 0f)
		{
			float2 /= num2;
		}
		else
		{
			float2.xz = startLine.b.xz - endLine.a.xz;
			num2 = math.length(float2.xz);
			if (num2 != 0f)
			{
				float2 /= num2;
			}
		}
		@float.y = math.clamp(@float.y, -1f, 1f);
		float2.y = math.clamp(float2.y, -1f, 1f);
		float num3 = math.acos(math.saturate(0f - math.dot(@float.xz, float2.xz)));
		float num4 = math.tan(num3 / 2f);
		float num5 = (num + num2) * (1f / 6f);
		num5 = ((!(num4 >= 0.0001f)) ? (num5 * 2f) : (num5 * (4f * math.tan(num3 / 4f) / num4)));
		return new Bezier4x3
		{
			a = startLine.a,
			b = startLine.a + @float * math.min(num, num5),
			c = endLine.a + float2 * math.min(num2, num5),
			d = endLine.a
		};
	}
```

- `public static FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Bezier4x3 FitCurve(Line3.Segment startLine, Line3.Segment endLine)
	{
		float3 @float = MathUtils.Tangent(startLine);
		float3 float2 = MathUtils.Tangent(endLine);
		float num = math.length(@float.xz);
		float num2 = math.length(float2.xz);
		if (num != 0f)
		{
			@float /= num;
		}
		else
		{
			@float.xz = endLine.b.xz - startLine.a.xz;
			num = math.length(@float.xz);
			if (num != 0f)
			{
				@float /= num;
			}
		}
		if (num2 != 0f)
		{
			float2 /= num2;
		}
		else
		{
			float2.xz = startLine.b.xz - endLine.a.xz;
			num2 = math.length(float2.xz);
			if (num2 != 0f)
			{
				float2 /= num2;
			}
		}
		@float.y = math.clamp(@float.y, -1f, 1f);
		float2.y = math.clamp(float2.y, -1f, 1f);
		float num3 = math.acos(math.saturate(0f - math.dot(@float.xz, float2.xz)));
		float num4 = math.tan(num3 / 2f);
		float num5 = (num + num2) * (1f / 6f);
		num5 = ((!(num4 >= 0.0001f)) ? (num5 * 2f) : (num5 * (4f * math.tan(num3 / 4f) / num4)));
		return new Bezier4x3
		{
			a = startLine.a,
			b = startLine.a + @float * math.min(num, num5),
			c = endLine.a + float2 * math.min(num2, num5),
			d = endLine.a
		};
	}
```

- `public static FitCurve(Colossal.Mathematics.Line3+Segment startLine, Colossal.Mathematics.Line3+Segment endLine) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Bezier4x3 FitCurve(Line3.Segment startLine, Line3.Segment endLine)
	{
		float3 @float = MathUtils.Tangent(startLine);
		float3 float2 = MathUtils.Tangent(endLine);
		float num = math.length(@float.xz);
		float num2 = math.length(float2.xz);
		if (num != 0f)
		{
			@float /= num;
		}
		else
		{
			@float.xz = endLine.b.xz - startLine.a.xz;
			num = math.length(@float.xz);
			if (num != 0f)
			{
				@float /= num;
			}
		}
		if (num2 != 0f)
		{
			float2 /= num2;
		}
		else
		{
			float2.xz = startLine.b.xz - endLine.a.xz;
			num2 = math.length(float2.xz);
			if (num2 != 0f)
			{
				float2 /= num2;
			}
		}
		@float.y = math.clamp(@float.y, -1f, 1f);
		float2.y = math.clamp(float2.y, -1f, 1f);
		float num3 = math.acos(math.saturate(0f - math.dot(@float.xz, float2.xz)));
		float num4 = math.tan(num3 / 2f);
		float num5 = (num + num2) * (1f / 6f);
		num5 = ((!(num4 >= 0.0001f)) ? (num5 * 2f) : (num5 * (4f * math.tan(num3 / 4f) / num4)));
		return new Bezier4x3
		{
			a = startLine.a,
			b = startLine.a + @float * math.min(num, num5),
			c = endLine.a + float2 * math.min(num2, num5),
			d = endLine.a
		};
	}
```

- `public static FlipUpgradeTrafficHandedness(Game.Prefabs.CompositionFlags& flags) : System.Void`  

```csharp
public static void FlipUpgradeTrafficHandedness(ref CompositionFlags flags)
	{
		uint bitMask = (uint)flags.m_Left;
		uint bitMask2 = (uint)flags.m_Right;
		CommonUtils.SwapBits(ref bitMask, 16777216u, 33554432u);
		CommonUtils.SwapBits(ref bitMask2, 16777216u, 33554432u);
		flags.m_Left = (CompositionFlags.Side)bitMask2;
		flags.m_Right = (CompositionFlags.Side)bitMask;
	}
```

- `public static GetAvailability(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Game.Net.AvailableResource resource, System.Single curvePos) : System.Single`  

```csharp
public static float GetAvailability(DynamicBuffer<ResourceAvailability> availabilities, AvailableResource resource, float curvePos)
	{
		if ((int)resource >= availabilities.Length)
		{
			return 0f;
		}
		float2 availability = availabilities[(int)resource].m_Availability;
		return math.lerp(availability.x, availability.y, curvePos);
	}
```

- `public static GetCollisionMask(Game.Prefabs.NetCompositionData compositionData, System.Boolean ignoreMarkers) : Game.Common.CollisionMask`  

```csharp
public static CollisionMask GetCollisionMask(LabelPosition labelPosition)
	{
		if (!labelPosition.m_IsUnderground)
		{
			return CollisionMask.Overground;
		}
		return CollisionMask.Underground;
	}
```

- `public static GetCollisionMask(Game.Net.LabelPosition labelPosition) : Game.Common.CollisionMask`  

```csharp
public static CollisionMask GetCollisionMask(LabelPosition labelPosition)
	{
		if (!labelPosition.m_IsUnderground)
		{
			return CollisionMask.Overground;
		}
		return CollisionMask.Underground;
	}
```

- `public static GetConstructionCost(Game.Net.Curve curve, Game.Net.Elevation startElevation, Game.Net.Elevation endElevation, Game.Prefabs.PlaceableNetComposition placeableNetData) : System.Int32`  

```csharp
public static int GetConstructionCost(Curve curve, Elevation startElevation, Elevation endElevation, PlaceableNetComposition placeableNetData)
	{
		int num = math.max(1, Mathf.RoundToInt(curve.m_Length / 8f));
		int num2 = math.max(0, Mathf.RoundToInt(math.max(math.cmin(startElevation.m_Elevation), math.cmin(endElevation.m_Elevation)) / 10f));
		return num * ((int)placeableNetData.m_ConstructionCost + num2 * (int)placeableNetData.m_ElevationCost);
	}
```

- `public static GetNodeRotation(Unity.Mathematics.float3 tangent) : Unity.Mathematics.quaternion`  

```csharp
public static quaternion GetNodeRotation(float3 tangent, quaternion defaultRotation)
	{
		tangent.y = 0f;
		if (MathUtils.TryNormalize(ref tangent))
		{
			return quaternion.LookRotation(tangent, math.up());
		}
		return defaultRotation;
	}
```

- `public static GetNodeRotation(Unity.Mathematics.float3 tangent, Unity.Mathematics.quaternion defaultRotation) : Unity.Mathematics.quaternion`  

```csharp
public static quaternion GetNodeRotation(float3 tangent, quaternion defaultRotation)
	{
		tangent.y = 0f;
		if (MathUtils.TryNormalize(ref tangent))
		{
			return quaternion.LookRotation(tangent, math.up());
		}
		return defaultRotation;
	}
```

- `public static GetParkingSlotCount(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane) : System.Int32`  

```csharp
public static int GetParkingSlotCount(Curve curve, ParkingLane parkingLane, ParkingLaneData prefabParkingLane)
	{
		return (int)math.floor((GetParkingSlotSpace(curve, parkingLane, prefabParkingLane) + 0.01f) / prefabParkingLane.m_SlotInterval);
	}
```

- `public static GetParkingSlotInterval(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane, System.Int32 slotCount) : System.Single`  

```csharp
public static float GetParkingSlotInterval(Curve curve, ParkingLane parkingLane, ParkingLaneData prefabParkingLane, int slotCount)
	{
		if (slotCount == 0 || (parkingLane.m_Flags & ParkingLaneFlags.FindConnections) != 0)
		{
			return prefabParkingLane.m_SlotInterval;
		}
		return GetParkingSlotSpace(curve, parkingLane, prefabParkingLane) / (float)slotCount;
	}
```

- `private static GetParkingSlotSpace(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane) : System.Single`  

```csharp
private static float GetParkingSlotSpace(Curve curve, ParkingLane parkingLane, ParkingLaneData prefabParkingLane)
	{
		float num = curve.m_Length;
		if ((parkingLane.m_Flags & ParkingLaneFlags.FindConnections) == 0)
		{
			num -= math.select(0f, 0.2f, (parkingLane.m_Flags & ParkingLaneFlags.StartingLane) != 0);
			num -= math.select(0f, 0.2f, (parkingLane.m_Flags & ParkingLaneFlags.EndingLane) != 0);
			if (prefabParkingLane.m_SlotAngle > 0.25f)
			{
				float num2 = math.min(math.dot(y: new float2(math.cos(prefabParkingLane.m_SlotAngle), math.sin(prefabParkingLane.m_SlotAngle)), x: prefabParkingLane.m_SlotSize), prefabParkingLane.m_SlotSize.y);
				switch (parkingLane.m_Flags & (ParkingLaneFlags.StartingLane | ParkingLaneFlags.EndingLane))
				{
				case ParkingLaneFlags.StartingLane:
				case ParkingLaneFlags.EndingLane:
					num -= num2 * 0.5f * math.tan(MathF.PI / 2f - prefabParkingLane.m_SlotAngle);
					break;
				case ParkingLaneFlags.StartingLane | ParkingLaneFlags.EndingLane:
					num -= num2 * math.tan(MathF.PI / 2f - prefabParkingLane.m_SlotAngle);
					break;
				}
			}
		}
		return num;
	}
```

- `public static GetRefundAmount(Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static int GetRefundAmount(Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		if ((float)simulationFrame < (float)recent.m_ModificationFrame + 262144f * economyParameterData.m_RoadRefundTimeRange.x)
		{
			return (int)((float)recent.m_ModificationCost * economyParameterData.m_RoadRefundPercentage.x);
		}
		if ((float)simulationFrame < (float)recent.m_ModificationFrame + 262144f * economyParameterData.m_RoadRefundTimeRange.y)
		{
			return (int)((float)recent.m_ModificationCost * economyParameterData.m_RoadRefundPercentage.y);
		}
		if ((float)simulationFrame < (float)recent.m_ModificationFrame + 262144f * economyParameterData.m_RoadRefundTimeRange.z)
		{
			return (int)((float)recent.m_ModificationCost * economyParameterData.m_RoadRefundPercentage.z);
		}
		return 0;
	}
```

- `public static GetServiceCoverage(Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> coverages, Game.Net.CoverageService service, System.Single curvePos) : System.Single`  

```csharp
public static float GetServiceCoverage(DynamicBuffer<ServiceCoverage> coverages, CoverageService service, float curvePos)
	{
		ServiceCoverage serviceCoverage = coverages[(int)service];
		return math.lerp(serviceCoverage.m_Coverage.x, serviceCoverage.m_Coverage.y, curvePos);
	}
```

- `public static GetSubNet(Unity.Entities.DynamicBuffer<Game.Prefabs.SubNet> subNets, System.Int32 index, System.Boolean lefthandTraffic, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryLookup) : Game.Prefabs.SubNet`  

```csharp
public static Game.Prefabs.SubNet GetSubNet(DynamicBuffer<Game.Prefabs.SubNet> subNets, int index, bool lefthandTraffic, ref ComponentLookup<NetGeometryData> netGeometryLookup)
	{
		Game.Prefabs.SubNet result = subNets[index];
		if (ShouldInvert(result.m_InvertMode, lefthandTraffic))
		{
			if (netGeometryLookup.TryGetComponent(result.m_Prefab, out var componentData) && (componentData.m_Flags & GeometryFlags.FlipTrafficHandedness) != 0)
			{
				result.m_Curve = MathUtils.Invert(result.m_Curve);
				result.m_NodeIndex = result.m_NodeIndex.yx;
				result.m_ParentMesh = result.m_ParentMesh.yx;
			}
			else
			{
				FlipUpgradeTrafficHandedness(ref result.m_Upgrades);
			}
		}
		return result;
	}
```

- `public static GetTerrainSmoothingWidth(Game.Prefabs.NetData netData) : System.Single`  

```csharp
public static float GetTerrainSmoothingWidth(NetData netData)
	{
		if ((netData.m_RequiredLayers & (Layer.Taxiway | Layer.MarkerTaxiway)) != Layer.None)
		{
			return 100f;
		}
		if ((netData.m_RequiredLayers & Layer.Waterway) != Layer.None)
		{
			return 20f;
		}
		return 8f;
	}
```

- `public static GetTrafficFlowSpeed(Game.Net.Road road) : Unity.Mathematics.float4`  

```csharp
public static float GetTrafficFlowSpeed(float duration, float distance)
	{
		return math.saturate(distance / duration);
	}
```

- `public static GetTrafficFlowSpeed(Unity.Mathematics.float4 duration, Unity.Mathematics.float4 distance) : Unity.Mathematics.float4`  

```csharp
public static float GetTrafficFlowSpeed(float duration, float distance)
	{
		return math.saturate(distance / duration);
	}
```

- `public static GetTrafficFlowSpeed(System.Single duration, System.Single distance) : System.Single`  

```csharp
public static float GetTrafficFlowSpeed(float duration, float distance)
	{
		return math.saturate(distance / duration);
	}
```

- `public static GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost) : System.Int32`  

```csharp
public static int GetUpgradeCost(int newCost, int oldCost, Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		if (newCost >= oldCost)
		{
			return GetUpgradeCost(newCost, oldCost);
		}
		recent.m_ModificationCost = math.min(recent.m_ModificationCost, oldCost - newCost);
		return -GetRefundAmount(recent, simulationFrame, economyParameterData);
	}
```

- `public static GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static int GetUpgradeCost(int newCost, int oldCost, Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		if (newCost >= oldCost)
		{
			return GetUpgradeCost(newCost, oldCost);
		}
		recent.m_ModificationCost = math.min(recent.m_ModificationCost, oldCost - newCost);
		return -GetRefundAmount(recent, simulationFrame, economyParameterData);
	}
```

- `public static GetUpkeepCost(Game.Net.Curve curve, Game.Prefabs.PlaceableNetComposition placeableNetData) : System.Int32`  

```csharp
public static int GetUpkeepCost(Curve curve, PlaceableNetComposition placeableNetData)
	{
		float num = math.max(1f, math.round(curve.m_Length / 8f));
		return math.max(1, Mathf.RoundToInt(num * placeableNetData.m_UpkeepCost));
	}
```

- `public static IsTurn(Unity.Mathematics.float2 startPosition, Unity.Mathematics.float2 startDirection, Unity.Mathematics.float2 endPosition, Unity.Mathematics.float2 endDirection, System.Boolean& right, System.Boolean& gentle, System.Boolean& uturn) : System.Boolean`  

```csharp
public static bool IsTurn(float2 startPosition, float2 startDirection, float2 endPosition, float2 endDirection, out bool right, out bool gentle, out bool uturn)
	{
		float2 x = MathUtils.Right(startDirection);
		float4 start = default(float4);
		start.y = math.dot(startDirection, endDirection);
		start.w = math.dot(x, endDirection);
		float num = math.distance(startPosition, endPosition);
		if (num > 0.1f)
		{
			float2 y = (startPosition - endPosition) / num;
			start.x = math.dot(startDirection, y);
			start.z = math.dot(x, y);
		}
		else
		{
			start.x = -1f;
			start.z = 0f;
		}
		start = math.lerp(start, new float4(-1f, -1f, start.wz), math.saturate(new float4(start.z * start.w * new float2(-2f, -4f), start.xy)));
		start = math.select(start, start.yxwz, start.y > start.x);
		right = start.z < 0f;
		gentle = (start.x > -0.9335804f) & (start.x <= -0.4848096f);
		uturn = start.x > 0.7547096f;
		return start.x > -0.9335804f;
	}
```

- `public static OffsetCurveLeftSmooth(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 offset) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Bezier4x3 OffsetCurveLeftSmooth(Bezier4x3 curve, float2 offset)
	{
		float3 value = MathUtils.StartTangent(curve);
		float3 value2 = MathUtils.Tangent(curve, 0.5f);
		float3 value3 = MathUtils.EndTangent(curve);
		value = MathUtils.Normalize(value, value.xz);
		value2 = MathUtils.Normalize(value2, value2.xz);
		value3 = MathUtils.Normalize(value3, value3.xz);
		value.y = math.clamp(value.y, -1f, 1f);
		value3.y = math.clamp(value3.y, -1f, 1f);
		float3 a = curve.a;
		float3 middlePos = MathUtils.Position(curve, 0.5f);
		float3 d = curve.d;
		float4 @float = new float4(-offset, offset);
		a.xz += value.zx * @float.xz;
		middlePos.xz += value2.zx * (@float.xz + @float.yw) * 0.5f;
		d.xz += value3.zx * @float.yw;
		return FitCurve(a, value, middlePos, value3, d);
	}
```

- `public static RemoveLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject) : System.Void`  

```csharp
public static void RemoveLaneObject(DynamicBuffer<LaneObject> buffer, Entity laneObject)
	{
		CollectionUtils.RemoveValue(buffer, new LaneObject(laneObject));
	}
```

- `public static ShouldInvert(Game.Prefabs.NetInvertMode invertMode, System.Boolean lefthandTraffic) : System.Boolean`  

```csharp
public static bool ShouldInvert(NetInvertMode invertMode, bool lefthandTraffic)
	{
		if (!(invertMode == NetInvertMode.LefthandTraffic && lefthandTraffic) && (invertMode != NetInvertMode.RighthandTraffic || lefthandTraffic))
		{
			return invertMode == NetInvertMode.Always;
		}
		return true;
	}
```

- `public static StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Bezier4x3 StraightCurve(float3 startPos, float3 endPos, float hanging)
	{
		Bezier4x3 result = new Bezier4x3
		{
			a = startPos,
			b = math.lerp(startPos, endPos, 1f / 3f),
			c = math.lerp(startPos, endPos, 2f / 3f),
			d = endPos
		};
		float num = math.distance(result.a.xz, result.d.xz) * hanging * 1.3333334f;
		result.b.y -= num;
		result.c.y -= num;
		return result;
	}
```

- `public static StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, System.Single hanging) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Bezier4x3 StraightCurve(float3 startPos, float3 endPos, float hanging)
	{
		Bezier4x3 result = new Bezier4x3
		{
			a = startPos,
			b = math.lerp(startPos, endPos, 1f / 3f),
			c = math.lerp(startPos, endPos, 2f / 3f),
			d = endPos
		};
		float num = math.distance(result.a.xz, result.d.xz) * hanging * 1.3333334f;
		result.b.y -= num;
		result.c.y -= num;
		return result;
	}
```

- `public static TryGetCombinedSegmentForLanes(Game.Net.EdgeGeometry edgeGeometry, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Net.Segment& segment) : System.Boolean`  

```csharp
public static bool TryGetCombinedSegmentForLanes(EdgeGeometry edgeGeometry, NetGeometryData prefabGeometryData, out Segment segment)
	{
		bool flag = (prefabGeometryData.m_Flags & (GeometryFlags.StraightEdges | GeometryFlags.SmoothSlopes)) == GeometryFlags.StraightEdges;
		segment = edgeGeometry.m_Start;
		segment.m_Left = MathUtils.Join(edgeGeometry.m_Start.m_Left, edgeGeometry.m_End.m_Left);
		segment.m_Right = MathUtils.Join(edgeGeometry.m_Start.m_Right, edgeGeometry.m_End.m_Right);
		segment.m_Length = edgeGeometry.m_Start.m_Length + edgeGeometry.m_End.m_Length;
		if (!flag && MathUtils.Length(MathUtils.Lerp(segment.m_Left.xz, segment.m_Right.xz, 0.5f)) <= prefabGeometryData.m_EdgeLengthRange.max * 0.5f)
		{
			float3 @float = default(float3);
			@float.x = MathUtils.Distance(segment.m_Left, MathUtils.Position(edgeGeometry.m_Start.m_Left, 0.5f), out var t);
			@float.y = MathUtils.Distance(segment.m_Left, edgeGeometry.m_Start.m_Left.d, out t);
			@float.z = MathUtils.Distance(segment.m_Left, MathUtils.Position(edgeGeometry.m_End.m_Left, 0.5f), out t);
			float3 float2 = default(float3);
			float2.x = MathUtils.Distance(segment.m_Right, MathUtils.Position(edgeGeometry.m_Start.m_Right, 0.5f), out t);
			float2.y = MathUtils.Distance(segment.m_Right, edgeGeometry.m_Start.m_Right.d, out t);
			float2.z = MathUtils.Distance(segment.m_Right, MathUtils.Position(edgeGeometry.m_End.m_Right, 0.5f), out t);
			flag = math.all((@float < 0.2f) & (float2 < 0.2f));
		}
		return flag;
	}
```

- `public static UpdateLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition) : System.Void`  

```csharp
public static void UpdateLaneObject(DynamicBuffer<LaneObject> buffer, Entity laneObject, float2 curvePosition)
	{
		LaneObject laneObject2 = new LaneObject(laneObject, curvePosition);
		for (int i = 0; i < buffer.Length; i++)
		{
			LaneObject laneObject3 = buffer[i];
			if (laneObject3.m_LaneObject == laneObject)
			{
				for (int j = i + 1; j < buffer.Length; j++)
				{
					laneObject3 = buffer[j];
					if (laneObject3.m_CurvePosition.y >= curvePosition.y)
					{
						buffer[j - 1] = laneObject2;
						return;
					}
					buffer[j - 1] = laneObject3;
				}
				buffer[buffer.Length - 1] = laneObject2;
				return;
			}
			if (!(laneObject3.m_CurvePosition.y >= curvePosition.y))
			{
				continue;
			}
			buffer[i] = laneObject2;
			laneObject2 = laneObject3;
			for (int k = i + 1; k < buffer.Length; k++)
			{
				laneObject3 = buffer[k];
				buffer[k] = laneObject2;
				laneObject2 = laneObject3;
				if (laneObject2.m_LaneObject == laneObject)
				{
					return;
				}
			}
			break;
		}
		buffer.Add(laneObject2);
	}
```


