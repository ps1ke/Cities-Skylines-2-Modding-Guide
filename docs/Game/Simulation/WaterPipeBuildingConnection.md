# Game.Simulation.WaterPipeBuildingConnection

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_ProducerEdge`  
- `public Unity.Entities.Entity m_ConsumerEdge`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetConsumerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.WaterPipeEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : Unity.Entities.Entity`  
- `public GetProducerNode(Unity.Entities.ComponentLookup`1[[Game.Simulation.WaterPipeEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : Unity.Entities.Entity`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

