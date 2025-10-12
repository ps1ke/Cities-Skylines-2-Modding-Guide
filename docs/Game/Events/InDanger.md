# Game.Events.InDanger

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Event`  
- `public Unity.Entities.Entity m_EvacuationRequest`  
- `public Game.Events.DangerFlags m_Flags`  
- `public System.UInt32 m_EndFrame`  

## Constructors

- `public InDanger(Unity.Entities.Entity _event, Unity.Entities.Entity evacuationRequest, Game.Events.DangerFlags flags, System.UInt32 endFrame)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

