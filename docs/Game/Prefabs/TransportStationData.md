# Game.Prefabs.TransportStationData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.TransportStationData>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Single m_ComfortFactor`  
- `public System.Single m_LoadingFactor`  
- `public Game.Vehicles.EnergyTypes m_CarRefuelTypes`  
- `public Game.Vehicles.EnergyTypes m_TrainRefuelTypes`  
- `public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes`  
- `public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes`  

## Methods

- `public Combine(Game.Prefabs.TransportStationData otherData) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

