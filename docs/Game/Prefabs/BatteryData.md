# Game.Prefabs.BatteryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.BatteryData>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_Capacity`  
- `public System.Int32 m_PowerOutput`  

## Properties

- `public System.Int64 capacityTicks { get }`  

## Methods

- `public Combine(Game.Prefabs.BatteryData otherData) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

