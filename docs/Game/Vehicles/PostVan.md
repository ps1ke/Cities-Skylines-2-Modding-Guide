# Game.Vehicles.PostVan

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_TargetRequest`  
- `public Game.Vehicles.PostVanFlags m_State`  
- `public System.Int32 m_RequestCount`  
- `public System.Single m_PathElementTime`  
- `public System.Int32 m_DeliveringMail`  
- `public System.Int32 m_CollectedMail`  
- `public System.Int32 m_DeliveryEstimate`  
- `public System.Int32 m_CollectEstimate`  

## Constructors

- `public PostVan(Game.Vehicles.PostVanFlags flags, System.Int32 requestCount, System.Int32 deliveringMail)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

