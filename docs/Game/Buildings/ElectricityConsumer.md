# Game.Buildings.ElectricityConsumer

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_WantedConsumption`  
- `public System.Int32 m_FulfilledConsumption`  
- `public System.Int16 m_CooldownCounter`  
- `public Game.Buildings.ElectricityConsumerFlags m_Flags`  

## Properties

- `public System.Boolean electricityConnected { get }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

