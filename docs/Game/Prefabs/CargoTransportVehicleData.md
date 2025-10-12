# Game.Prefabs.CargoTransportVehicleData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Economy.Resource m_Resources`  
- `public System.Int32 m_CargoCapacity`  
- `public System.Int32 m_MaxResourceCount`  
- `public System.Single m_MaintenanceRange`  

## Constructors

- `public CargoTransportVehicleData(Game.Economy.Resource resources, System.Int32 cargoCapacity, System.Int32 maxResourceCount, System.Single maintenanceRange)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

