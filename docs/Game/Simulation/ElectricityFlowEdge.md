# Game.Simulation.ElectricityFlowEdge

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_Index`  
- `public Unity.Entities.Entity m_Start`  
- `public Unity.Entities.Entity m_End`  
- `public System.Int32 m_Capacity`  
- `public System.Int32 m_Flow`  
- `public Game.Simulation.ElectricityFlowEdgeFlags m_Flags`  

## Properties

- `public Game.Net.FlowDirection direction { get; set }`  
- `public System.Boolean isBottleneck { get }`  
- `public System.Boolean isBeyondBottleneck { get }`  
- `public System.Boolean isDisconnected { get }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

