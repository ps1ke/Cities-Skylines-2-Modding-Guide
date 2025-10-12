# Game.Simulation.PostVanRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Target`  
- `public Game.Simulation.PostVanRequestFlags m_Flags`  
- `public System.Byte m_DispatchIndex`  
- `public System.UInt16 m_Priority`  

## Constructors

- `public PostVanRequest(Unity.Entities.Entity target, Game.Simulation.PostVanRequestFlags flags, System.UInt16 priority)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

