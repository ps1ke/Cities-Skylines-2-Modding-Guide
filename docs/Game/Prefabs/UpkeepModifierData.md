# Game.Prefabs.UpkeepModifierData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Game.Prefabs.ICombineBuffer<Game.Prefabs.UpkeepModifierData>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Economy.Resource m_Resource`  
- `public System.Single m_Multiplier`  

## Methods

- `public Combine(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> result) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public Transform(System.Single upkeep) : System.Single`  

