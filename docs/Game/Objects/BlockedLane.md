# Game.Objects.BlockedLane

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Objects.BlockedLane>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Unity.Entities.Entity m_Lane`  
- `public Unity.Mathematics.float2 m_CurvePosition`  

## Constructors

- `public BlockedLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePosition)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Equals(Game.Objects.BlockedLane other) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

