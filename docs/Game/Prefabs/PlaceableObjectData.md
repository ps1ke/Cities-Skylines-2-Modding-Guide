# Game.Prefabs.PlaceableObjectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Mathematics.float3 m_PlacementOffset`  
- `public System.UInt32 m_ConstructionCost`  
- `public System.Int32 m_XPReward`  
- `public System.Byte m_DefaultProbability`  
- `public Game.Objects.RotationSymmetry m_RotationSymmetry`  
- `public Game.Net.SubReplacementType m_SubReplacementType`  
- `public Game.Objects.PlacementFlags m_Flags`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

