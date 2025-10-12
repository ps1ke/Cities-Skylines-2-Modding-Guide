# Game.Prefabs.ConsumptionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.ConsumptionData>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_Upkeep`  
- `public System.Single m_ElectricityConsumption`  
- `public System.Single m_WaterConsumption`  
- `public System.Single m_GarbageAccumulation`  
- `public System.Single m_TelecomNeed`  

## Methods

- `public AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public Combine(Game.Prefabs.ConsumptionData otherData) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

