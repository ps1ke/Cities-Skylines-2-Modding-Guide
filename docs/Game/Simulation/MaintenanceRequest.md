# Game.Simulation.MaintenanceRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Target`  
- `public System.Int32 m_Priority`  
- `public System.Byte m_DispatchIndex`  

## Constructors

- `public MaintenanceRequest(Unity.Entities.Entity target, System.Int32 priority)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

