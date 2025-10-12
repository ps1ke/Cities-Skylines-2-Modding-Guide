# Game.Vehicles.Ambulance

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Vehicles.AmbulanceFlags m_State`  
- `public Unity.Entities.Entity m_TargetPatient`  
- `public Unity.Entities.Entity m_TargetLocation`  
- `public Unity.Entities.Entity m_TargetRequest`  
- `public System.Single m_PathElementTime`  

## Constructors

- `public Ambulance(Unity.Entities.Entity targetPatient, Unity.Entities.Entity targetLocation, Game.Vehicles.AmbulanceFlags state)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

