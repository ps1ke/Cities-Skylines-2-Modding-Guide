# Game.Simulation.GarbageTransferRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Facility`  
- `public Game.Simulation.GarbageTransferRequestFlags m_Flags`  
- `public System.Single m_Priority`  
- `public System.Int32 m_Amount`  

## Constructors

- `public GarbageTransferRequest(Unity.Entities.Entity facility, Game.Simulation.GarbageTransferRequestFlags flags, System.Single priority, System.Int32 amount)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

