# Game.Simulation.HealthcareRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Citizen`  
- `public Game.Simulation.HealthcareRequestType m_Type`  

## Constructors

- `public HealthcareRequest(Unity.Entities.Entity citizen, Game.Simulation.HealthcareRequestType type)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

