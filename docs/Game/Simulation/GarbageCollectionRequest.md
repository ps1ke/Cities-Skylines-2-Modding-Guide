# Game.Simulation.GarbageCollectionRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Target`  
- `public System.Int32 m_Priority`  
- `public Game.Simulation.GarbageCollectionRequestFlags m_Flags`  
- `public System.Byte m_DispatchIndex`  

## Constructors

- `public GarbageCollectionRequest(Unity.Entities.Entity target, System.Int32 priority, Game.Simulation.GarbageCollectionRequestFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

