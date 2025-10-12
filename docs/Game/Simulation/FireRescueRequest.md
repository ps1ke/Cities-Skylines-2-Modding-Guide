# Game.Simulation.FireRescueRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Target`  
- `public System.Single m_Priority`  
- `public Game.Simulation.FireRescueRequestType m_Type`  

## Constructors

- `public FireRescueRequest(Unity.Entities.Entity target, System.Single priority, Game.Simulation.FireRescueRequestType type)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

