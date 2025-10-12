# Game.Net.NetUtils

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Single DEFAULT_ELEVATION_STEP`  
- `public static const System.Single MAX_LANE_WEAR`  
- `public static const System.Single MAX_LOCAL_CONNECT_DISTANCE`  
- `public static const System.Single MAX_LOCAL_CONNECT_HEIGHT`  
- `public static const System.Single MAX_SNAP_HEIGHT`  
- `public static const System.Single UTURN_LIMIT_COS`  
- `public static const System.Single TURN_LIMIT_COS`  
- `public static const System.Single GENTLETURN_LIMIT_COS`  
- `public static const System.Single MAX_PASSING_CURVINESS_STREET`  
- `public static const System.Single MAX_PASSING_CURVINESS_HIGHWAY`  
- `public static const System.Single MIN_VISIBLE_EDGE_LENGTH`  
- `public static const System.Single MIN_VISIBLE_NODE_LENGTH`  
- `public static const System.Single MIN_VISIBLE_LANE_LENGTH`  

## Methods

- `public static AddLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition) : System.Void`  
- `public static AdjustPosition(Game.Net.Node node, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Net.Node`  
- `public static AdjustPosition(Game.Net.Node node, Game.Buildings.BuildingUtils+LotInfo& lotInfo) : Game.Net.Node`  
- `public static AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Net.Curve`  
- `public static AdjustPosition(Game.Net.Curve curve, System.Boolean fixedStart, System.Boolean linearMiddle, System.Boolean fixedEnd, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData) : Game.Net.Curve`  
- `public static AdjustPosition(Game.Net.Curve curve, Unity.Mathematics.bool2 fixedStart, System.Boolean linearMiddle, Unity.Mathematics.bool2 fixedEnd, Game.Buildings.BuildingUtils+LotInfo& lotInfo) : Game.Net.Curve`  
- `public static CalculateCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  
- `public static CalculateCurviness(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 position2, Unity.Mathematics.float3 tangent2) : System.Single`  
- `public static CalculateCurviness(Unity.Mathematics.float3 tangent1, Unity.Mathematics.float3 tangent2, System.Single distance) : System.Single`  
- `public static CalculateEndCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  
- `public static CalculateStartCurviness(Game.Net.Curve curve, System.Single width) : System.Single`  
- `public static CanConnect(Game.Prefabs.NetData netData1, Game.Prefabs.NetData netData2) : System.Boolean`  
- `public static ChooseClosestLane(System.Int32 minIndex, System.Int32 maxIndex, Unity.Mathematics.float3 comparePosition, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, System.Single curvePosition) : System.Int32`  
- `public static CircleCurve(Unity.Mathematics.float3 center, System.Single xOffset, System.Single zOffset) : Colossal.Mathematics.Bezier4x3`  
- `public static CircleCurve(Unity.Mathematics.float3 center, Unity.Mathematics.quaternion rotation, System.Single xOffset, System.Single zOffset) : Colossal.Mathematics.Bezier4x3`  
- `public static ExtendedClampLength(Colossal.Mathematics.Bezier4x2 curve, System.Single distance) : System.Single`  
- `public static ExtendedDistance(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 position, System.Single& t) : System.Single`  
- `public static ExtendedLength(Colossal.Mathematics.Bezier4x2 curve, System.Single t) : System.Single`  
- `public static ExtendedPositionAndTangent(Colossal.Mathematics.Bezier4x3 curve, System.Single t, Unity.Mathematics.float3& position, Unity.Mathematics.float3& tangent) : System.Void`  
- `public static FindConnectedLane(Unity.Entities.Entity& laneEntity, System.Boolean& forward, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  
- `public static FindEdgeLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, System.Boolean startNode) : System.Boolean`  
- `public static FindMiddleTangentPos(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 offset) : System.Single`  
- `public static FindNextLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  
- `public static FindPrevLane(Unity.Entities.Entity& entity, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Boolean`  
- `public static FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 middlePos, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  
- `public static FitCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 startTangent, Unity.Mathematics.float3 endTangent, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  
- `public static FitCurve(Colossal.Mathematics.Line3+Segment startLine, Colossal.Mathematics.Line3+Segment endLine) : Colossal.Mathematics.Bezier4x3`  
- `public static FlipUpgradeTrafficHandedness(Game.Prefabs.CompositionFlags& flags) : System.Void`  
- `public static GetAvailability(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Game.Net.AvailableResource resource, System.Single curvePos) : System.Single`  
- `public static GetCollisionMask(Game.Prefabs.NetCompositionData compositionData, System.Boolean ignoreMarkers) : Game.Common.CollisionMask`  
- `public static GetCollisionMask(Game.Net.LabelPosition labelPosition) : Game.Common.CollisionMask`  
- `public static GetConstructionCost(Game.Net.Curve curve, Game.Net.Elevation startElevation, Game.Net.Elevation endElevation, Game.Prefabs.PlaceableNetComposition placeableNetData) : System.Int32`  
- `public static GetNodeRotation(Unity.Mathematics.float3 tangent) : Unity.Mathematics.quaternion`  
- `public static GetNodeRotation(Unity.Mathematics.float3 tangent, Unity.Mathematics.quaternion defaultRotation) : Unity.Mathematics.quaternion`  
- `public static GetParkingSlotCount(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane) : System.Int32`  
- `public static GetParkingSlotInterval(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane, System.Int32 slotCount) : System.Single`  
- `private static GetParkingSlotSpace(Game.Net.Curve curve, Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData prefabParkingLane) : System.Single`  
- `public static GetRefundAmount(Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  
- `public static GetServiceCoverage(Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> coverages, Game.Net.CoverageService service, System.Single curvePos) : System.Single`  
- `public static GetSubNet(Unity.Entities.DynamicBuffer<Game.Prefabs.SubNet> subNets, System.Int32 index, System.Boolean lefthandTraffic, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryLookup) : Game.Prefabs.SubNet`  
- `public static GetTerrainSmoothingWidth(Game.Prefabs.NetData netData) : System.Single`  
- `public static GetTrafficFlowSpeed(Game.Net.Road road) : Unity.Mathematics.float4`  
- `public static GetTrafficFlowSpeed(Unity.Mathematics.float4 duration, Unity.Mathematics.float4 distance) : Unity.Mathematics.float4`  
- `public static GetTrafficFlowSpeed(System.Single duration, System.Single distance) : System.Single`  
- `public static GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost) : System.Int32`  
- `public static GetUpgradeCost(System.Int32 newCost, System.Int32 oldCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  
- `public static GetUpkeepCost(Game.Net.Curve curve, Game.Prefabs.PlaceableNetComposition placeableNetData) : System.Int32`  
- `public static IsTurn(Unity.Mathematics.float2 startPosition, Unity.Mathematics.float2 startDirection, Unity.Mathematics.float2 endPosition, Unity.Mathematics.float2 endDirection, System.Boolean& right, System.Boolean& gentle, System.Boolean& uturn) : System.Boolean`  
- `public static OffsetCurveLeftSmooth(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 offset) : Colossal.Mathematics.Bezier4x3`  
- `public static RemoveLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject) : System.Void`  
- `public static ShouldInvert(Game.Prefabs.NetInvertMode invertMode, System.Boolean lefthandTraffic) : System.Boolean`  
- `public static StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos) : Colossal.Mathematics.Bezier4x3`  
- `public static StraightCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, System.Single hanging) : Colossal.Mathematics.Bezier4x3`  
- `public static TryGetCombinedSegmentForLanes(Game.Net.EdgeGeometry edgeGeometry, Game.Prefabs.NetGeometryData prefabGeometryData, Game.Net.Segment& segment) : System.Boolean`  
- `public static UpdateLaneObject(Unity.Entities.DynamicBuffer<Game.Net.LaneObject> buffer, Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition) : System.Void`  

