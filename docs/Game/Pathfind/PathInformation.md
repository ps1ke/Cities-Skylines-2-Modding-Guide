# Game.Pathfind.PathInformation

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Origin`  
- `public Unity.Entities.Entity m_Destination`  
- `public System.Single m_Distance`  
- `public System.Single m_Duration`  
- `public System.Single m_TotalCost`  
- `public Game.Pathfind.PathMethod m_Methods`  
- `public Game.Pathfind.PathFlags m_State`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

