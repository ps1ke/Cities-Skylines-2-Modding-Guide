# Game.Prefabs.NetCompositionHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NetCompositionHelpers
{
    public static System.Void AddCompositionLanes<TNetCompositionPieceList>(Unity.Entities.Entity entity, Game.Prefabs.NetCompositionData& compositionData, TNetCompositionPieceList pieces, Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> netLanes, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionCarriageway> carriageways, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
    public static System.Void CalculateCompositionData(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
    private static System.Void CalculateCompositionPieceOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData);
    public static System.Void CalculateMinLod(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> meshDatas);
    public static System.Void CalculatePlaceableData(Game.Prefabs.PlaceableNetComposition& placeableData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetPieceData> placeableNetPieceData);
    public static System.Void CalculateRoundaboutSize(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
    private static System.Void CalculateSyncVertexOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData);
    private static System.Int32 FindClosestLane(Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> lanes, System.Int32 startIndex, Unity.Mathematics.float3 position, Game.Prefabs.LaneFlags flags);
    public static System.Void GetCompositionPieces(Unity.Collections.NativeList<Game.Prefabs.NetCompositionPiece> resultBuffer, Unity.Collections.NativeArray<Game.Prefabs.NetGeometrySection> geometrySections, Game.Prefabs.CompositionFlags flags, Unity.Entities.BufferLookup<Game.Prefabs.NetSubSection> subSectionData, Unity.Entities.BufferLookup<Game.Prefabs.NetSectionPiece> sectionPieceData);
    public static Game.Prefabs.CompositionFlags GetElevationFlags(Game.Net.Elevation startElevation, Game.Net.Elevation middleElevation, Game.Net.Elevation endElevation, Game.Prefabs.NetGeometryData prefabGeometryData);
    public static System.Void GetRequirementFlags(Game.Prefabs.NetPieceRequirements[] requirements, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags);
    public static System.Void GetRequirementFlags(Game.Prefabs.NetPieceRequirements requirement, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags);
    private static System.Boolean HasRoad(Unity.Entities.Entity piece, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
    public static Game.Prefabs.CompositionFlags InvertCompositionFlags(Game.Prefabs.CompositionFlags flags);
    public static Game.Prefabs.NetSectionFlags InvertSectionFlags(Game.Prefabs.NetSectionFlags flags);
    public static System.Boolean TestEdgeFlags(Game.Prefabs.NetGeometryEdgeState edgeState, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestEdgeFlags(Game.Prefabs.NetGeometryNodeState nodeState, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestEdgeFlags(Game.Prefabs.ElectricityConnectionData electricityConnectionData, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestEdgeMatch(Game.Prefabs.NetGeometryNodeState nodeState, Unity.Mathematics.bool2 match);
    public static System.Boolean TestLaneFlags(Game.Prefabs.AuxiliaryNetLane lane, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestObjectFlags(Game.Prefabs.NetPieceObject _object, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
    public static System.Boolean TestPieceFlags(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
    public static System.Boolean TestPieceFlags2(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
    public static System.Boolean TestSectionFlags(Game.Prefabs.NetGeometrySection section, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestSubSectionFlags(Game.Prefabs.NetSubSection subSection, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
}
```


## Methods

- `public static AddCompositionLanes<TNetCompositionPieceList>(Unity.Entities.Entity entity, Game.Prefabs.NetCompositionData& compositionData, TNetCompositionPieceList pieces, Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> netLanes, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionCarriageway> carriageways, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  

```csharp
public static System.Void AddCompositionLanes<TNetCompositionPieceList>(Unity.Entities.Entity entity, Game.Prefabs.NetCompositionData& compositionData, TNetCompositionPieceList pieces, Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> netLanes, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionCarriageway> carriageways, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
```

- `public static CalculateCompositionData(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  

```csharp
public static System.Void CalculateCompositionData(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
```

- `private static CalculateCompositionPieceOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData) : System.Void`  

```csharp
private static System.Void CalculateCompositionPieceOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData);
```

- `public static CalculateMinLod(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> meshDatas) : System.Void`  

```csharp
public static System.Void CalculateMinLod(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> meshDatas);
```

- `public static CalculatePlaceableData(Game.Prefabs.PlaceableNetComposition& placeableData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetPieceData> placeableNetPieceData) : System.Void`  

```csharp
public static System.Void CalculatePlaceableData(Game.Prefabs.PlaceableNetComposition& placeableData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetPieceData> placeableNetPieceData);
```

- `public static CalculateRoundaboutSize(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  

```csharp
public static System.Void CalculateRoundaboutSize(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
```

- `private static CalculateSyncVertexOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData) : System.Void`  

```csharp
private static System.Void CalculateSyncVertexOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData);
```

- `private static FindClosestLane(Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> lanes, System.Int32 startIndex, Unity.Mathematics.float3 position, Game.Prefabs.LaneFlags flags) : System.Int32`  

```csharp
private static System.Int32 FindClosestLane(Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> lanes, System.Int32 startIndex, Unity.Mathematics.float3 position, Game.Prefabs.LaneFlags flags);
```

- `public static GetCompositionPieces(Unity.Collections.NativeList<Game.Prefabs.NetCompositionPiece> resultBuffer, Unity.Collections.NativeArray<Game.Prefabs.NetGeometrySection> geometrySections, Game.Prefabs.CompositionFlags flags, Unity.Entities.BufferLookup<Game.Prefabs.NetSubSection> subSectionData, Unity.Entities.BufferLookup<Game.Prefabs.NetSectionPiece> sectionPieceData) : System.Void`  

```csharp
public static System.Void GetCompositionPieces(Unity.Collections.NativeList<Game.Prefabs.NetCompositionPiece> resultBuffer, Unity.Collections.NativeArray<Game.Prefabs.NetGeometrySection> geometrySections, Game.Prefabs.CompositionFlags flags, Unity.Entities.BufferLookup<Game.Prefabs.NetSubSection> subSectionData, Unity.Entities.BufferLookup<Game.Prefabs.NetSectionPiece> sectionPieceData);
```

- `public static GetElevationFlags(Game.Net.Elevation startElevation, Game.Net.Elevation middleElevation, Game.Net.Elevation endElevation, Game.Prefabs.NetGeometryData prefabGeometryData) : Game.Prefabs.CompositionFlags`  

```csharp
public static Game.Prefabs.CompositionFlags GetElevationFlags(Game.Net.Elevation startElevation, Game.Net.Elevation middleElevation, Game.Net.Elevation endElevation, Game.Prefabs.NetGeometryData prefabGeometryData);
```

- `public static GetRequirementFlags(Game.Prefabs.NetPieceRequirements[] requirements, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags) : System.Void`  

```csharp
public static System.Void GetRequirementFlags(Game.Prefabs.NetPieceRequirements[] requirements, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags);
```

- `public static GetRequirementFlags(Game.Prefabs.NetPieceRequirements requirement, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags) : System.Void`  

```csharp
public static System.Void GetRequirementFlags(Game.Prefabs.NetPieceRequirements requirement, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags);
```

- `private static HasRoad(Unity.Entities.Entity piece, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Boolean`  

```csharp
private static System.Boolean HasRoad(Unity.Entities.Entity piece, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
```

- `public static InvertCompositionFlags(Game.Prefabs.CompositionFlags flags) : Game.Prefabs.CompositionFlags`  

```csharp
public static Game.Prefabs.CompositionFlags InvertCompositionFlags(Game.Prefabs.CompositionFlags flags);
```

- `public static InvertSectionFlags(Game.Prefabs.NetSectionFlags flags) : Game.Prefabs.NetSectionFlags`  

```csharp
public static Game.Prefabs.NetSectionFlags InvertSectionFlags(Game.Prefabs.NetSectionFlags flags);
```

- `public static TestEdgeFlags(Game.Prefabs.NetGeometryEdgeState edgeState, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestEdgeFlags(Game.Prefabs.NetGeometryEdgeState edgeState, Game.Prefabs.CompositionFlags compositionFlags);
```

- `public static TestEdgeFlags(Game.Prefabs.NetGeometryNodeState nodeState, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestEdgeFlags(Game.Prefabs.NetGeometryNodeState nodeState, Game.Prefabs.CompositionFlags compositionFlags);
```

- `public static TestEdgeFlags(Game.Prefabs.ElectricityConnectionData electricityConnectionData, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestEdgeFlags(Game.Prefabs.ElectricityConnectionData electricityConnectionData, Game.Prefabs.CompositionFlags compositionFlags);
```

- `public static TestEdgeMatch(Game.Prefabs.NetGeometryNodeState nodeState, Unity.Mathematics.bool2 match) : System.Boolean`  

```csharp
public static System.Boolean TestEdgeMatch(Game.Prefabs.NetGeometryNodeState nodeState, Unity.Mathematics.bool2 match);
```

- `public static TestLaneFlags(Game.Prefabs.AuxiliaryNetLane lane, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestLaneFlags(Game.Prefabs.AuxiliaryNetLane lane, Game.Prefabs.CompositionFlags compositionFlags);
```

- `public static TestObjectFlags(Game.Prefabs.NetPieceObject _object, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestObjectFlags(Game.Prefabs.NetPieceObject _object, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
```

- `public static TestPieceFlags(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestPieceFlags(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
```

- `public static TestPieceFlags2(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestPieceFlags2(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
```

- `public static TestSectionFlags(Game.Prefabs.NetGeometrySection section, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestSectionFlags(Game.Prefabs.NetGeometrySection section, Game.Prefabs.CompositionFlags compositionFlags);
```

- `public static TestSubSectionFlags(Game.Prefabs.NetSubSection subSection, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

```csharp
public static System.Boolean TestSubSectionFlags(Game.Prefabs.NetSubSection subSection, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
```


## Nested types

- `Game.Prefabs.NetCompositionHelpers+TempLaneData`  
- `Game.Prefabs.NetCompositionHelpers+TempLaneGroup`  

