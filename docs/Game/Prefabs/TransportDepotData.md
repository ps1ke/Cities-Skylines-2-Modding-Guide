# Game.Prefabs.TransportDepotData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.TransportDepotData>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Prefabs.TransportType m_TransportType`  
- `public Game.Vehicles.EnergyTypes m_EnergyTypes`  
- `public Game.Vehicles.SizeClass m_SizeClass`  
- `public System.Boolean m_DispatchCenter`  
- `public System.Int32 m_VehicleCapacity`  
- `public System.Single m_ProductionDuration`  
- `public System.Single m_MaintenanceDuration`  

## Methods

- `public Combine(Game.Prefabs.TransportDepotData otherData) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

