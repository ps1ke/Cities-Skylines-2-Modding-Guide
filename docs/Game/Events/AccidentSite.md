# Game.Events.AccidentSite

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Event`  
- `public Unity.Entities.Entity m_PoliceRequest`  
- `public Game.Events.AccidentSiteFlags m_Flags`  
- `public System.UInt32 m_CreationFrame`  
- `public System.UInt32 m_SecuredFrame`  

## Constructors

- `public AccidentSite(Unity.Entities.Entity _event, Game.Events.AccidentSiteFlags flags, System.UInt32 currentFrame)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

