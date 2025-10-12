# Game.Buildings.GarbageFacility

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_GarbageDeliverRequest`  
- `public Unity.Entities.Entity m_GarbageReceiveRequest`  
- `public Unity.Entities.Entity m_TargetRequest`  
- `public Game.Buildings.GarbageFacilityFlags m_Flags`  
- `public System.Single m_AcceptGarbagePriority`  
- `public System.Single m_DeliverGarbagePriority`  
- `public System.Int32 m_ProcessingRate`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

