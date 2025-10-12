# Game.Vehicles.MaintenanceVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_TargetRequest`  
- `public Game.Vehicles.MaintenanceVehicleFlags m_State`  
- `public System.Int32 m_Maintained`  
- `public System.Int32 m_MaintainEstimate`  
- `public System.Int32 m_RequestCount`  
- `public System.Single m_PathElementTime`  
- `public System.Single m_Efficiency`  

## Constructors

- `public MaintenanceVehicle(Game.Vehicles.MaintenanceVehicleFlags flags, System.Int32 requestCount, System.Single efficiency)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

