# Game.Prefabs.PublicTransportVehicleData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Prefabs.TransportType m_TransportType`  
- `public System.Int32 m_PassengerCapacity`  
- `public Game.Prefabs.PublicTransportPurpose m_PurposeMask`  
- `public System.Single m_MaintenanceRange`  

## Constructors

- `public PublicTransportVehicleData(Game.Prefabs.TransportType type, System.Int32 passengerCapacity, Game.Prefabs.PublicTransportPurpose purposeMask, System.Single maintenanceRange)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

