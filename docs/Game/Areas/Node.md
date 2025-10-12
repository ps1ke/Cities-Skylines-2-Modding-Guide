# Game.Areas.Node

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Unity.Mathematics.float3 m_Position`  
- `public System.Single m_Elevation`  

## Constructors

- `public Node(Unity.Mathematics.float3 position, System.Single elevation)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

