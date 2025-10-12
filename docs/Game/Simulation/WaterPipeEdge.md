# Game.Simulation.WaterPipeEdge

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_Index`  
- `public Unity.Entities.Entity m_Start`  
- `public Unity.Entities.Entity m_End`  
- `public System.Int32 m_FreshFlow`  
- `public System.Single m_FreshPollution`  
- `public System.Int32 m_SewageFlow`  
- `public System.Int32 m_FreshCapacity`  
- `public System.Int32 m_SewageCapacity`  
- `public Game.Simulation.WaterPipeEdgeFlags m_Flags`  

## Properties

- `public Unity.Mathematics.int2 flow { get }`  
- `public Unity.Mathematics.int2 capacity { get }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

