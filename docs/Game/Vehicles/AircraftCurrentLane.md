# Game.Vehicles.AircraftCurrentLane

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Lane`  
- `public Unity.Mathematics.float3 m_CurvePosition`  
- `public Game.Vehicles.AircraftLaneFlags m_LaneFlags`  
- `public System.Single m_Duration`  
- `public System.Single m_Distance`  
- `public System.Single m_LanePosition`  

## Constructors

- `public AircraftCurrentLane(Game.Vehicles.ParkedCar parkedCar, Game.Vehicles.AircraftLaneFlags flags)`  
- `public AircraftCurrentLane(Game.Pathfind.PathElement pathElement, Game.Vehicles.AircraftLaneFlags laneFlags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

