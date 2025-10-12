# Game.Zones.VacantLot

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Zones.VacantLot>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Unity.Mathematics.int4 m_Area`  
- `public Game.Zones.ZoneType m_Type`  
- `public System.Int16 m_Height`  
- `public Game.Zones.LotFlags m_Flags`  

## Constructors

- `public VacantLot(Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, Game.Zones.ZoneType type, System.Int32 height, Game.Zones.LotFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Equals(Game.Zones.VacantLot other) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

