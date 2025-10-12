# Game.Routes.TransportLine

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_VehicleRequest`  
- `public System.Single m_VehicleInterval`  
- `public System.Single m_UnbunchingFactor`  
- `public Game.Routes.TransportLineFlags m_Flags`  
- `public System.UInt16 m_TicketPrice`  

## Constructors

- `public TransportLine(Game.Prefabs.TransportLineData transportLineData)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

