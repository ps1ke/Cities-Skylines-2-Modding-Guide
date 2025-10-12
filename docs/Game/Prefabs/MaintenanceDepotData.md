# Game.Prefabs.MaintenanceDepotData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.MaintenanceDepotData>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Simulation.MaintenanceType m_MaintenanceType`  
- `public System.Int32 m_VehicleCapacity`  
- `public System.Single m_VehicleEfficiency`  

## Methods

- `public Combine(Game.Prefabs.MaintenanceDepotData otherData) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

