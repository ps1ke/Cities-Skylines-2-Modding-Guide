# Game.Creatures.CurrentVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Vehicle`  
- `public Game.Creatures.CreatureVehicleFlags m_Flags`  

## Constructors

- `public CurrentVehicle(Unity.Entities.Entity vehicle, Game.Creatures.CreatureVehicleFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

