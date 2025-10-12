# Game.Pathfind.PathElement

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Unity.Entities.Entity m_Target`  
- `public Unity.Mathematics.float2 m_TargetDelta`  
- `public Game.Pathfind.PathElementFlags m_Flags`  

## Constructors

- `public PathElement(Unity.Entities.Entity target, Unity.Mathematics.float2 targetDelta, Game.Pathfind.PathElementFlags flags = 0)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

