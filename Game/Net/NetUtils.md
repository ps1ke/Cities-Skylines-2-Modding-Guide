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
public static System.Void AddLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition);
```

- `public static AdjustPosition(Game.Net.Node node, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Net.Node`  

```csharp
public static Game.Net.Node AdjustPosition(Game.Net.Node node, Game.Simulation.TerrainHeightData& terrainHeightData);
```

- `public static AdjustPosition(Game.Net.Node node, Game.Buildings.BuildingUtils+LotInfo& lotInfo) : Game.Net.Node`  

```csharp
public static Game.Net.Node AdjustPosition(Game.Net.Node node, Game.Buildings.BuildingUtils+LotInfo& lotInfo);
```

- `public static AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Net.Curve`  

```csharp
public static Game.Net.Curve AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData);
```

- `public static AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData) : Game.Net.Curve`  

```csharp
public static Game.Net.Curve AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData);
```

- `public static AdjustPosition(Game.Net.Curve curve, Unity.Mathematics.bool2 fixedStart, System.Boolean linearMiddle, Unity.Mathematics.bool2 fixedEnd, Game.Buildings.BuildingUtils+LotInfo& lotInfo) : Game.Net.Curve`  

```csharp
public static Game.Net.Curve AdjustPosition(Game.Net.Curve curve, Unity.Mathematics.bool2 fixedStart, System.Boolean linearMiddle, Unity.Mathematics.bool2 fixedEnd, Game.Buildings.BuildingUtils+LotInfo& lotInfo);
```

- `public static CalculateCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  

```csharp
public static System.Single CalculateCurviness(Game.Net.Curve curve, System.Single width);
```

- `public static CalculateCurviness(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 position2, Unity.Mathematics.float3 tangent2) : System.Single`  

```csharp
public static System.Single CalculateCurviness(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 position2, Unity.Mathematics.float3 tangent2);
```

- `public static CalculateCurviness(Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 tangent2, System.Single distance) : System.Single`  

```csharp
public static System.Single CalculateCurviness(Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 tangent2, System.Single distance);
```

- `public static CalculateEndCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  

```csharp
public static System.Single CalculateEndCurviness(Game.Net.Curve curve, System.Single width);
```

- `public static CalculateStartCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  

```csharp
public static System.Single CalculateStartCurviness(Game.Net.Curve curve, System.Single width);
```

- `public static CanConnect(Game.Prefabs.NetData netData1, Game.Prefabs.NetData netData2) : System.Boolean`  

```csharp
public static System.Boolean CanConnect(Game.Prefabs.NetData netData1, Game.Prefabs.NetData netData2);
```

- `public static ChooseClosestLane(System.Int32 minIndex, System.Int32 maxIndex, Unity.Mathematics.float3 comparePosition, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, System.Single curvePosition) : System.Int32`  

```csharp
public static System.Int32 ChooseClosestLane(System.Int32 minIndex, System.Int32 maxIndex, Unity.Mathematics.float3 comparePosition, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, System.Single curvePosition);
```

- `public static CircleCurve(Unity.Mathematics.float3 center, System.Single xOffset, System.Single zOffset) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 CircleCurve(Unity.Mathematics.float3 center, System.Single xOffset, System.Single zOffset);
```

- `public static CircleCurve(Unity.Mathematics.float3 center, Unity.Mathematics.quaternion rotation, System.Single xOffset, System.Single zOffset) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 CircleCurve(Unity.Mathematics.float3 center, Unity.Mathematics.quaternion rotation, System.Single xOffset, System.Single zOffset);
```

- `public static ExtendedClampLength(Colossal.Mathematics.Bezier4x2 curve, System.Single distance) : System.Single`  

```csharp
public static System.Single ExtendedClampLength(Colossal.Mathematics.Bezier4x2 curve, System.Single distance);
```

- `public static ExtendedDistance(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 position, System.Single& t) : System.Single`  

```csharp
public static System.Single ExtendedDistance(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 position, System.Single& t);
```

- `public static ExtendedLength(Colossal.Mathematics.Bezier4x2 curve, System.Single t) : System.Single`  

```csharp
public static System.Single ExtendedLength(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
```

- `public static ExtendedPositionAndTangent(Colossal.Mathematics.Bezier4x3 curve, System.Single t, Unity.Mathematics.float3& position, Unity.Mathematics.float3& tangent) : System.Void`  

```csharp
public static System.Void ExtendedPositionAndTangent(Colossal.Mathematics.Bezier4x3 curve, System.Single t, Unity.Mathematics.float3& position, Unity.Mathematics.float3& tangent);
```

- `public static FindConnectedLane(Unity.Entities.Entity& laneEntity, System.Boolean& forward, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  

```csharp
public static System.Boolean FindConnectedLane(Unity.Entities.Entity& laneEntity, System.Boolean& forward, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
```

- `public static FindEdgeLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, System.Boolean startNode) : System.Boolean`  

```csharp
public static System.Boolean FindEdgeLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, System.Boolean startNode);
```

- `public static FindMiddleTangentPos(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 offset) : System.Single`  

```csharp
public static System.Single FindMiddleTangentPos(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 offset);
```

- `public static FindNextLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  

```csharp
public static System.Boolean FindNextLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
```

- `public static FindPrevLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  

```csharp
public static System.Boolean FindPrevLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
```

- `public static FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 middlePos, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 middlePos, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos);
```

- `public static FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos);
```

- `public static FitCurve(Colossal.Mathematics.Line3+Segment startLine, Colossal.Mathematics.Line3+Segment endLine) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 FitCurve(Colossal.Mathematics.Line3+Segment startLine, Colossal.Mathematics.Line3+Segment endLine);
```

- `public static FlipUpgradeTrafficHandedness(Game.Prefabs.CompositionFlags& flags) : System.Void`  

```csharp
public static System.Void FlipUpgradeTrafficHandedness(Game.Prefabs.CompositionFlags& flags);
```

- `public static GetAvailability(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Game.Net.AvailableResource resource, System.Single curvePos) : System.Single`  

```csharp
public static System.Single GetAvailability(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Game.Net.AvailableResource resource, System.Single curvePos);
```

- `public static GetCollisionMask(Game.Prefabs.NetCompositionData compositionData, System.Boolean ignoreMarkers) : Game.Common.CollisionMask`  

```csharp
public static Game.Common.CollisionMask GetCollisionMask(Game.Prefabs.NetCompositionData compositionData, System.Boolean ignoreMarkers);
```

- `public static GetCollisionMask(Game.Net.LabelPosition labelPosition) : Game.Common.CollisionMask`  

```csharp
public static Game.Common.CollisionMask GetCollisionMask(Game.Net.LabelPosition labelPosition);
```

- `public static GetConstructionCost(Game.Net.Curve curve, Game.Net.Elevation startElevation, Game.Net.Elevation endElevation, Game.Prefabs.PlaceableNetComposition placeableNetData) : System.Int32`  

```csharp
public static System.Int32 GetConstructionCost(Game.Net.Curve curve, Game.Net.Elevation startElevation, Game.Net.Elevation endElevation, Game.Prefabs.PlaceableNetComposition placeableNetData);
```

- `public static GetNodeRotation(Unity.Mathematics.float3 tangent) : Unity.Mathematics.quaternion`  

```csharp
public static Unity.Mathematics.quaternion GetNodeRotation(Unity.Mathematics.float3 tangent);
```

- `public static GetNodeRotation(Unity.Mathematics.float3 tangent, Unity.Mathematics.quaternion defaultRotation) : Unity.Mathematics.quaternion`  

```csharp
public static Unity.Mathematics.quaternion GetNodeRotation(Unity.Mathematics.float3 tangent, Unity.Mathematics.quaternion defaultRotation);
```

- `public static GetParkingSlotCount(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane) : System.Int32`  

```csharp
public static System.Int32 GetParkingSlotCount(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane);
```

- `public static GetParkingSlotInterval(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane, System.Int32 slotCount) : System.Single`  

```csharp
public static System.Single GetParkingSlotInterval(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane, System.Int32 slotCount);
```

- `private static GetParkingSlotSpace(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane) : System.Single`  

```csharp
private static System.Single GetParkingSlotSpace(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane);
```

- `public static GetRefundAmount(Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static System.Int32 GetRefundAmount(Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData);
```

- `public static GetServiceCoverage(Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> coverages, Game.Net.CoverageService service, System.Single curvePos) : System.Single`  

```csharp
public static System.Single GetServiceCoverage(Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> coverages, Game.Net.CoverageService service, System.Single curvePos);
```

- `public static GetSubNet(Unity.Entities.DynamicBuffer<Game.Prefabs.SubNet> subNets, System.Int32 index, System.Boolean lefthandTraffic, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryLookup) : Game.Prefabs.SubNet`  

```csharp
public static Game.Prefabs.SubNet GetSubNet(Unity.Entities.DynamicBuffer<Game.Prefabs.SubNet> subNets, System.Int32 index, System.Boolean lefthandTraffic, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryLookup);
```

- `public static GetTerrainSmoothingWidth(Game.Prefabs.NetData netData) : System.Single`  

```csharp
public static System.Single GetTerrainSmoothingWidth(Game.Prefabs.NetData netData);
```

- `public static GetTrafficFlowSpeed(Game.Net.Road road) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 GetTrafficFlowSpeed(Game.Net.Road road);
```

- `public static GetTrafficFlowSpeed(Unity.Mathematics.float4 duration, Unity.Mathematics.float4 distance) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 GetTrafficFlowSpeed(Unity.Mathematics.float4 duration, Unity.Mathematics.float4 distance);
```

- `public static GetTrafficFlowSpeed(System.Single duration, System.Single distance) : System.Single`  

```csharp
public static System.Single GetTrafficFlowSpeed(System.Single duration, System.Single distance);
```

- `public static GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost) : System.Int32`  

```csharp
public static System.Int32 GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost);
```

- `public static GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static System.Int32 GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData);
```

- `public static GetUpkeepCost(Game.Net.Curve curve, Game.Prefabs.PlaceableNetComposition placeableNetData) : System.Int32`  

```csharp
public static System.Int32 GetUpkeepCost(Game.Net.Curve curve, Game.Prefabs.PlaceableNetComposition placeableNetData);
```

- `public static IsTurn(Unity.Mathematics.float2 startPosition, Unity.Mathematics.float2 startDirection, Unity.Mathematics.float2 endPosition, Unity.Mathematics.float2 endDirection, System.Boolean& right, System.Boolean& gentle, System.Boolean& uturn) : System.Boolean`  

```csharp
public static System.Boolean IsTurn(Unity.Mathematics.float2 startPosition, Unity.Mathematics.float2 startDirection, Unity.Mathematics.float2 endPosition, Unity.Mathematics.float2 endDirection, System.Boolean& right, System.Boolean& gentle, System.Boolean& uturn);
```

- `public static OffsetCurveLeftSmooth(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 offset) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 OffsetCurveLeftSmooth(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 offset);
```

- `public static RemoveLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject) : System.Void`  

```csharp
public static System.Void RemoveLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject);
```

- `public static ShouldInvert(Game.Prefabs.NetInvertMode invertMode, System.Boolean lefthandTraffic) : System.Boolean`  

```csharp
public static System.Boolean ShouldInvert(Game.Prefabs.NetInvertMode invertMode, System.Boolean lefthandTraffic);
```

- `public static StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos);
```

- `public static StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, System.Single hanging) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, System.Single hanging);
```

- `public static TryGetCombinedSegmentForLanes(Game.Net.EdgeGeometry edgeGeometry, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Net.Segment& segment) : System.Boolean`  

```csharp
public static System.Boolean TryGetCombinedSegmentForLanes(Game.Net.EdgeGeometry edgeGeometry, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Net.Segment& segment);
```

- `public static UpdateLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition) : System.Void`  

```csharp
public static System.Void UpdateLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition);
```


