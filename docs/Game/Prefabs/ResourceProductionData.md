# Game.Prefabs.ResourceProductionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Game.Economy.Resource m_Type`  
- `public System.Int32 m_ProductionRate`  
- `public System.Int32 m_StorageCapacity`  

## Constructors

- `public ResourceProductionData(Game.Economy.Resource type, System.Int32 productionRate, System.Int32 storageCapacity)`  

## Methods

- `public static Combine(Unity.Collections.NativeList<Game.Prefabs.ResourceProductionData> resources, Unity.Entities.DynamicBuffer<Game.Prefabs.ResourceProductionData> others) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

