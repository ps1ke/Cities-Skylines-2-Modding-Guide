# Game.Pathfind.PathNode

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Pathfind.PathNode>`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private System.UInt64 m_SearchKey`  
- `private static const System.Single FLOAT_TO_INT`  
- `private static const System.Single INT_TO_FLOAT`  
- `private static const System.UInt64 CURVEPOS_INCLUDE`  
- `private static const System.UInt64 CURVEPOS_EXCLUDE`  
- `private static const System.UInt64 SECONDARY_NODE`  

## Constructors

- `public PathNode(Unity.Entities.Entity owner, System.Byte laneIndex, System.Byte segmentIndex)`  
- `public PathNode(Unity.Entities.Entity owner, System.Byte laneIndex, System.Byte segmentIndex, System.Single curvePosition)`  
- `public PathNode(Unity.Entities.Entity owner, System.UInt16 laneIndex, System.Single curvePosition)`  
- `public PathNode(Unity.Entities.Entity owner, System.UInt16 laneIndex)`  
- `public PathNode(Game.Pathfind.PathTarget pathTarget)`  
- `public PathNode(Game.Pathfind.PathNode pathNode, System.Single curvePosition)`  
- `public PathNode(Game.Pathfind.PathNode pathNode, System.Boolean secondaryNode)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Equals(Game.Pathfind.PathNode other) : System.Boolean`  
- `public EqualsIgnoreCurvePos(Game.Pathfind.PathNode other) : System.Boolean`  
- `public GetCurvePos() : System.Single`  
- `public GetCurvePosOrder(Game.Pathfind.PathNode other) : System.Int32`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetLaneIndex() : System.UInt16`  
- `public GetOrder(Game.Pathfind.PathNode other) : System.Boolean`  
- `public GetOwnerIndex() : System.Int32`  
- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  
- `public IsSecondary() : System.Boolean`  
- `public OwnerEquals(Game.Pathfind.PathNode other) : System.Boolean`  
- `public ReplaceOwner(Unity.Entities.Entity oldOwner, Unity.Entities.Entity newOwner) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetOwner(Unity.Entities.Entity newOwner) : System.Void`  
- `public SetSegmentIndex(System.Byte segmentIndex) : System.Void`  
- `public StripCurvePos() : Game.Pathfind.PathNode`  

