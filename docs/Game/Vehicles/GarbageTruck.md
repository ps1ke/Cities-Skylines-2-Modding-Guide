# Game.Vehicles.GarbageTruck

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_TargetRequest`  
- `public Game.Vehicles.GarbageTruckFlags m_State`  
- `public System.Int32 m_RequestCount`  
- `public System.Int32 m_Garbage`  
- `public System.Int32 m_EstimatedGarbage`  
- `public System.Single m_PathElementTime`  

## Constructors

- `public GarbageTruck(Game.Vehicles.GarbageTruckFlags flags, System.Int32 requestCount)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

