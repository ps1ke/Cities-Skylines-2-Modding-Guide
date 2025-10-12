# Game.Vehicles.Hearse

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Vehicles.HearseFlags m_State`  
- `public Unity.Entities.Entity m_TargetCorpse`  
- `public Unity.Entities.Entity m_TargetRequest`  
- `public System.Single m_PathElementTime`  

## Constructors

- `public Hearse(Unity.Entities.Entity targetCorpse, Game.Vehicles.HearseFlags state)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

