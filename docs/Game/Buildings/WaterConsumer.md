# Game.Buildings.WaterConsumer

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Single m_Pollution`  
- `public System.Int32 m_WantedConsumption`  
- `public System.Int32 m_FulfilledFresh`  
- `public System.Int32 m_FulfilledSewage`  
- `public System.Byte m_FreshCooldownCounter`  
- `public System.Byte m_SewageCooldownCounter`  
- `public Game.Buildings.WaterConsumerFlags m_Flags`  

## Properties

- `public System.Boolean waterConnected { get }`  
- `public System.Boolean sewageConnected { get }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

