# Game.Simulation.RandomTrafficRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Target`  
- `public Game.Net.RoadTypes m_RoadType`  
- `public Game.Net.TrackTypes m_TrackType`  
- `public Game.Vehicles.EnergyTypes m_EnergyTypes`  
- `public Game.Vehicles.SizeClass m_SizeClass`  
- `public Game.Simulation.RandomTrafficRequestFlags m_Flags`  

## Constructors

- `public RandomTrafficRequest(Unity.Entities.Entity target, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Simulation.RandomTrafficRequestFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

