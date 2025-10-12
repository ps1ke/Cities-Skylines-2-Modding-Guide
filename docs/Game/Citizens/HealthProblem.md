# Game.Citizens.HealthProblem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Event`  
- `public Unity.Entities.Entity m_HealthcareRequest`  
- `public Game.Citizens.HealthProblemFlags m_Flags`  
- `public System.Byte m_Timer`  

## Constructors

- `public HealthProblem(Unity.Entities.Entity _event, Game.Citizens.HealthProblemFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

