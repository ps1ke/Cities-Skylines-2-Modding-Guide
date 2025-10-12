# Game.Events.InvolvedInAccident

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Event`  
- `public System.Single m_Severity`  
- `public System.UInt32 m_InvolvedFrame`  

## Constructors

- `public InvolvedInAccident(Unity.Entities.Entity _event, System.Single severity, System.UInt32 simulationFrame)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

