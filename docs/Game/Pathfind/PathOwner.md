# Game.Pathfind.PathOwner

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_ElementIndex`  
- `public Game.Pathfind.PathFlags m_State`  

## Constructors

- `public PathOwner(Game.Pathfind.PathFlags state)`  
- `public PathOwner(System.Int32 elementIndex, Game.Pathfind.PathFlags state)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

