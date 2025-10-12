# Game.Events.OnFire

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Event`  
- `public Unity.Entities.Entity m_RescueRequest`  
- `public System.Single m_Intensity`  
- `public System.UInt32 m_RequestFrame`  

## Constructors

- `public OnFire(Unity.Entities.Entity _event, System.Single intensity, System.UInt32 requestFrame = 0)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

