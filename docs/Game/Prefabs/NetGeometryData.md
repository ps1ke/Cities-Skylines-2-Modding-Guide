# Game.Prefabs.NetGeometryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.EntityArchetype m_NodeCompositionArchetype`  
- `public Unity.Entities.EntityArchetype m_EdgeCompositionArchetype`  
- `public Unity.Entities.Entity m_AggregateType`  
- `public Unity.Entities.Entity m_StyleType`  
- `public Colossal.Mathematics.Bounds1 m_DefaultHeightRange`  
- `public Colossal.Mathematics.Bounds1 m_ElevatedHeightRange`  
- `public Colossal.Mathematics.Bounds1 m_DefaultSurfaceHeight`  
- `public Colossal.Mathematics.Bounds1 m_EdgeLengthRange`  
- `public Game.Net.Layer m_MergeLayers`  
- `public Game.Net.Layer m_IntersectLayers`  
- `public Game.Net.GeometryFlags m_Flags`  
- `public System.Single m_DefaultWidth`  
- `public System.Single m_ElevatedWidth`  
- `public System.Single m_ElevatedLength`  
- `public System.Single m_MinNodeOffset`  
- `public System.Single m_ElevationLimit`  
- `public System.Single m_MaxSlopeSteepness`  
- `public System.Single m_Hanging`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

