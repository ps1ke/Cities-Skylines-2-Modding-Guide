# Game.Vehicles.FireEngine

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_TargetRequest`  
- `public Game.Vehicles.FireEngineFlags m_State`  
- `public System.Int32 m_RequestCount`  
- `public System.Single m_PathElementTime`  
- `public System.Single m_ExtinguishingAmount`  
- `public System.Single m_Efficiency`  

## Constructors

- `public FireEngine(Game.Vehicles.FireEngineFlags state, System.Int32 requestCount, System.Single extinguishingAmount, System.Single efficiency)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

