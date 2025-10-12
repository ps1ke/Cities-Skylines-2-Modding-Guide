# Game.Simulation.TaxiRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Seeker`  
- `public Unity.Entities.Entity m_District1`  
- `public Unity.Entities.Entity m_District2`  
- `public System.Int32 m_Priority`  
- `public Game.Simulation.TaxiRequestType m_Type`  

## Constructors

- `public TaxiRequest(Unity.Entities.Entity seeker, Unity.Entities.Entity district1, Unity.Entities.Entity district2, Game.Simulation.TaxiRequestType type, System.Int32 priority)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

