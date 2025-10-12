# Game.Net.LaneSignal

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Petitioner`  
- `public Unity.Entities.Entity m_Blocker`  
- `public System.UInt16 m_GroupMask`  
- `public System.SByte m_Priority`  
- `public System.SByte m_Default`  
- `public Game.Net.LaneSignalType m_Signal`  
- `public Game.Net.LaneSignalFlags m_Flags`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

