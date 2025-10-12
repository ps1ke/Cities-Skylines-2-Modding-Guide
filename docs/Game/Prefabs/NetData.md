# Game.Prefabs.NetData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.EntityArchetype m_NodeArchetype`  
- `public Unity.Entities.EntityArchetype m_EdgeArchetype`  
- `public Game.Net.Layer m_RequiredLayers`  
- `public Game.Net.Layer m_ConnectLayers`  
- `public Game.Net.Layer m_LocalConnectLayers`  
- `public Game.Prefabs.CompositionFlags+General m_GeneralFlagMask`  
- `public Game.Prefabs.CompositionFlags+Side m_SideFlagMask`  
- `public System.Single m_NodePriority`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

