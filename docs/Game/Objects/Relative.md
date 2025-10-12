# Game.Objects.Relative

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Mathematics.float3 m_Position`  
- `public Unity.Mathematics.quaternion m_Rotation`  
- `public Unity.Mathematics.int3 m_BoneIndex`  

## Constructors

- `public Relative(Game.Objects.Transform localTransform, Unity.Mathematics.int3 boneIndex)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public ToTransform() : Game.Objects.Transform`  

