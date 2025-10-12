# Game.Prefabs.MaintenanceVehicleData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Simulation.MaintenanceType m_MaintenanceType`  
- `public System.Int32 m_MaintenanceCapacity`  
- `public System.Int32 m_MaintenanceRate`  

## Constructors

- `public MaintenanceVehicleData(Game.Simulation.MaintenanceType maintenanceType, System.Int32 maintenanceCapacity, System.Int32 maintenanceRate)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

