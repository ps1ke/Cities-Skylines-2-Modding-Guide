# Game.Vehicles.PoliceCar

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_TargetRequest`  
- `public Game.Vehicles.PoliceCarFlags m_State`  
- `public System.Int32 m_RequestCount`  
- `public System.Single m_PathElementTime`  
- `public System.UInt32 m_ShiftTime`  
- `public System.UInt32 m_EstimatedShift`  
- `public Game.Prefabs.PolicePurpose m_PurposeMask`  

## Constructors

- `public PoliceCar(Game.Vehicles.PoliceCarFlags flags, System.Int32 requestCount, Game.Prefabs.PolicePurpose purposeMask)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

