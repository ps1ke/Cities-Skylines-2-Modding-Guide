# Game.Triggers.Chirp

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Sender`  
- `public System.UInt32 m_CreationFrame`  
- `public System.UInt32 m_Likes`  
- `public System.UInt32 m_TargetLikes`  
- `public System.UInt32 m_InactiveFrame`  
- `public System.Int32 m_ViralFactor`  
- `public System.Single m_ContinuousFactor`  
- `public Game.Triggers.ChirpFlags m_Flags`  

## Constructors

- `public Chirp(Unity.Entities.Entity sender, System.UInt32 creationFrame)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

