# Game.Simulation.PoliceEmergencyRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Site`  
- `public Unity.Entities.Entity m_Target`  
- `public System.Single m_Priority`  
- `public Game.Prefabs.PolicePurpose m_Purpose`  

## Constructors

- `public PoliceEmergencyRequest(Unity.Entities.Entity site, Unity.Entities.Entity target, System.Single priority, Game.Prefabs.PolicePurpose purpose)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

