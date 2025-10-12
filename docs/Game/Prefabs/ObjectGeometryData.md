# Game.Prefabs.ObjectGeometryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  
- `public Unity.Mathematics.float3 m_Size`  
- `public Unity.Mathematics.float3 m_Pivot`  
- `public Unity.Mathematics.float3 m_LegSize`  
- `public Unity.Mathematics.float2 m_LegOffset`  
- `public Game.Objects.GeometryFlags m_Flags`  
- `public System.Int32 m_MinLod`  
- `public Game.Prefabs.MeshLayer m_Layers`  
- `public Game.Prefabs.ObjectRequirementFlags m_SubObjectMask`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

