# Game.Pathfind.PathNode

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Pathfind.PathNode>`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PathNode : System.IEquatable<Game.Pathfind.PathNode>, Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    private System.UInt64 m_SearchKey;
    private static const System.Single FLOAT_TO_INT;
    private static const System.Single INT_TO_FLOAT;
    private static const System.UInt64 CURVEPOS_INCLUDE;
    private static const System.UInt64 CURVEPOS_EXCLUDE;
    private static const System.UInt64 SECONDARY_NODE;

    public PathNode(Unity.Entities.Entity owner, System.Byte laneIndex, System.Byte segmentIndex);
    public PathNode(Unity.Entities.Entity owner, System.Byte laneIndex, System.Byte segmentIndex, System.Single curvePosition);
    public PathNode(Unity.Entities.Entity owner, System.UInt16 laneIndex, System.Single curvePosition);
    public PathNode(Unity.Entities.Entity owner, System.UInt16 laneIndex);
    public PathNode(Game.Pathfind.PathTarget pathTarget);
    public PathNode(Game.Pathfind.PathNode pathNode, System.Single curvePosition);
    public PathNode(Game.Pathfind.PathNode pathNode, System.Boolean secondaryNode);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Pathfind.PathNode other);
    public System.Boolean EqualsIgnoreCurvePos(Game.Pathfind.PathNode other);
    public System.Single GetCurvePos();
    public System.Int32 GetCurvePosOrder(Game.Pathfind.PathNode other);
    public virtual System.Int32 GetHashCode();
    public System.UInt16 GetLaneIndex();
    public System.Boolean GetOrder(Game.Pathfind.PathNode other);
    public System.Int32 GetOwnerIndex();
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Boolean IsSecondary();
    public System.Boolean OwnerEquals(Game.Pathfind.PathNode other);
    public System.Void ReplaceOwner(Unity.Entities.Entity oldOwner, Unity.Entities.Entity newOwner);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetOwner(Unity.Entities.Entity newOwner);
    public System.Void SetSegmentIndex(System.Byte segmentIndex);
    public Game.Pathfind.PathNode StripCurvePos();
}
```


## Fields

- `private System.UInt64 m_SearchKey`  

```csharp
private System.UInt64 m_SearchKey;
```

- `private static const System.Single FLOAT_TO_INT`  

```csharp
private static const System.Single FLOAT_TO_INT;
```

- `private static const System.Single INT_TO_FLOAT`  

```csharp
private static const System.Single INT_TO_FLOAT;
```

- `private static const System.UInt64 CURVEPOS_INCLUDE`  

```csharp
private static const System.UInt64 CURVEPOS_INCLUDE;
```

- `private static const System.UInt64 CURVEPOS_EXCLUDE`  

```csharp
private static const System.UInt64 CURVEPOS_EXCLUDE;
```

- `private static const System.UInt64 SECONDARY_NODE`  

```csharp
private static const System.UInt64 SECONDARY_NODE;
```


## Constructors

- `public PathNode(Unity.Entities.Entity owner, System.Byte laneIndex, System.Byte segmentIndex)`  

```csharp
public PathNode(Unity.Entities.Entity owner, System.Byte laneIndex, System.Byte segmentIndex);
```

- `public PathNode(Unity.Entities.Entity owner, System.Byte laneIndex, System.Byte segmentIndex, System.Single curvePosition)`  

```csharp
public PathNode(Unity.Entities.Entity owner, System.Byte laneIndex, System.Byte segmentIndex, System.Single curvePosition);
```

- `public PathNode(Unity.Entities.Entity owner, System.UInt16 laneIndex, System.Single curvePosition)`  

```csharp
public PathNode(Unity.Entities.Entity owner, System.UInt16 laneIndex, System.Single curvePosition);
```

- `public PathNode(Unity.Entities.Entity owner, System.UInt16 laneIndex)`  

```csharp
public PathNode(Unity.Entities.Entity owner, System.UInt16 laneIndex);
```

- `public PathNode(Game.Pathfind.PathTarget pathTarget)`  

```csharp
public PathNode(Game.Pathfind.PathTarget pathTarget);
```

- `public PathNode(Game.Pathfind.PathNode pathNode, System.Single curvePosition)`  

```csharp
public PathNode(Game.Pathfind.PathNode pathNode, System.Single curvePosition);
```

- `public PathNode(Game.Pathfind.PathNode pathNode, System.Boolean secondaryNode)`  

```csharp
public PathNode(Game.Pathfind.PathNode pathNode, System.Boolean secondaryNode);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Pathfind.PathNode other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Pathfind.PathNode other);
```

- `public EqualsIgnoreCurvePos(Game.Pathfind.PathNode other) : System.Boolean`  

```csharp
public System.Boolean EqualsIgnoreCurvePos(Game.Pathfind.PathNode other);
```

- `public GetCurvePos() : System.Single`  

```csharp
public System.Single GetCurvePos();
```

- `public GetCurvePosOrder(Game.Pathfind.PathNode other) : System.Int32`  

```csharp
public System.Int32 GetCurvePosOrder(Game.Pathfind.PathNode other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public GetLaneIndex() : System.UInt16`  

```csharp
public System.UInt16 GetLaneIndex();
```

- `public GetOrder(Game.Pathfind.PathNode other) : System.Boolean`  

```csharp
public System.Boolean GetOrder(Game.Pathfind.PathNode other);
```

- `public GetOwnerIndex() : System.Int32`  

```csharp
public System.Int32 GetOwnerIndex();
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public IsSecondary() : System.Boolean`  

```csharp
public System.Boolean IsSecondary();
```

- `public OwnerEquals(Game.Pathfind.PathNode other) : System.Boolean`  

```csharp
public System.Boolean OwnerEquals(Game.Pathfind.PathNode other);
```

- `public ReplaceOwner(Unity.Entities.Entity oldOwner, Unity.Entities.Entity newOwner) : System.Void`  

```csharp
public System.Void ReplaceOwner(Unity.Entities.Entity oldOwner, Unity.Entities.Entity newOwner);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetOwner(Unity.Entities.Entity newOwner) : System.Void`  

```csharp
public System.Void SetOwner(Unity.Entities.Entity newOwner);
```

- `public SetSegmentIndex(System.Byte segmentIndex) : System.Void`  

```csharp
public System.Void SetSegmentIndex(System.Byte segmentIndex);
```

- `public StripCurvePos() : Game.Pathfind.PathNode`  

```csharp
public Game.Pathfind.PathNode StripCurvePos();
```


