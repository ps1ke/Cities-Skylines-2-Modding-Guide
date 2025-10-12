# Game.Prefabs.ZoneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Zones.ZoneType m_ZoneType`  
- `public Game.Zones.AreaType m_AreaType`  
- `public Game.Prefabs.ZoneFlags m_ZoneFlags`  
- `public System.UInt16 m_MinOddHeight`  
- `public System.UInt16 m_MinEvenHeight`  
- `public System.UInt16 m_MaxHeight`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public IsOffice() : System.Boolean`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

