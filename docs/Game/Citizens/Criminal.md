# Game.Citizens.Criminal

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Event`  
- `public System.UInt16 m_JailTime`  
- `public Game.Citizens.CriminalFlags m_Flags`  

## Constructors

- `public Criminal(Unity.Entities.Entity _event, Game.Citizens.CriminalFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

