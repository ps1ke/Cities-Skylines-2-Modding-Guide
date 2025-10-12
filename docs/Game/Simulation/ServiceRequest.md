# Game.Simulation.ServiceRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Byte m_FailCount`  
- `public System.Byte m_Cooldown`  
- `public Game.Simulation.ServiceRequestFlags m_Flags`  

## Constructors

- `public ServiceRequest(System.Boolean reversed)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

