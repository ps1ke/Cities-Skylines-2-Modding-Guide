# Game.Objects.Transform

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Objects.Transform>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Mathematics.float3 m_Position`  
- `public Unity.Mathematics.quaternion m_Rotation`  

## Constructors

- `public Transform(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Equals(Game.Objects.Transform other) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

