# Game.Prefabs.NetCompositionHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static AddCompositionLanes<TNetCompositionPieceList>(Unity.Entities.Entity entity, Game.Prefabs.NetCompositionData& compositionData, TNetCompositionPieceList pieces, Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> netLanes, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionCarriageway> carriageways, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  
- `public static CalculateCompositionData(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  
- `private static CalculateCompositionPieceOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData) : System.Void`  
- `public static CalculateMinLod(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> meshDatas) : System.Void`  
- `public static CalculatePlaceableData(Game.Prefabs.PlaceableNetComposition& placeableData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetPieceData> placeableNetPieceData) : System.Void`  
- `public static CalculateRoundaboutSize(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  
- `private static CalculateSyncVertexOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData) : System.Void`  
- `private static FindClosestLane(Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> lanes, System.Int32 startIndex, Unity.Mathematics.float3 position, Game.Prefabs.LaneFlags flags) : System.Int32`  
- `public static GetCompositionPieces(Unity.Collections.NativeList<Game.Prefabs.NetCompositionPiece> resultBuffer, Unity.Collections.NativeArray<Game.Prefabs.NetGeometrySection> geometrySections, Game.Prefabs.CompositionFlags flags, Unity.Entities.BufferLookup<Game.Prefabs.NetSubSection> subSectionData, Unity.Entities.BufferLookup<Game.Prefabs.NetSectionPiece> sectionPieceData) : System.Void`  
- `public static GetElevationFlags(Game.Net.Elevation startElevation, Game.Net.Elevation middleElevation, Game.Net.Elevation endElevation, Game.Prefabs.NetGeometryData prefabGeometryData) : Game.Prefabs.CompositionFlags`  
- `public static GetRequirementFlags(Game.Prefabs.NetPieceRequirements[] requirements, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags) : System.Void`  
- `public static GetRequirementFlags(Game.Prefabs.NetPieceRequirements requirement, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags) : System.Void`  
- `private static HasRoad(Unity.Entities.Entity piece, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Boolean`  
- `public static InvertCompositionFlags(Game.Prefabs.CompositionFlags flags) : Game.Prefabs.CompositionFlags`  
- `public static InvertSectionFlags(Game.Prefabs.NetSectionFlags flags) : Game.Prefabs.NetSectionFlags`  
- `public static TestEdgeFlags(Game.Prefabs.NetGeometryEdgeState edgeState, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  
- `public static TestEdgeFlags(Game.Prefabs.NetGeometryNodeState nodeState, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  
- `public static TestEdgeFlags(Game.Prefabs.ElectricityConnectionData electricityConnectionData, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  
- `public static TestEdgeMatch(Game.Prefabs.NetGeometryNodeState nodeState, Unity.Mathematics.bool2 match) : System.Boolean`  
- `public static TestLaneFlags(Game.Prefabs.AuxiliaryNetLane lane, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  
- `public static TestObjectFlags(Game.Prefabs.NetPieceObject _object, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  
- `public static TestPieceFlags(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  
- `public static TestPieceFlags2(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  
- `public static TestSectionFlags(Game.Prefabs.NetGeometrySection section, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  
- `public static TestSubSectionFlags(Game.Prefabs.NetSubSection subSection, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

## Nested types

- `Game.Prefabs.NetCompositionHelpers+TempLaneData`  
- `Game.Prefabs.NetCompositionHelpers+TempLaneGroup`  

