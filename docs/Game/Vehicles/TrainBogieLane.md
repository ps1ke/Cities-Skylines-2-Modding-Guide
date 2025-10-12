# Game.Vehicles.TrainBogieLane

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Lane`  
- `public Unity.Mathematics.float4 m_CurvePosition`  
- `public Game.Vehicles.TrainLaneFlags m_LaneFlags`  

## Constructors

- `public TrainBogieLane(Game.Vehicles.TrainBogieCache cache)`  
- `public TrainBogieLane(Unity.Entities.Entity lane, Unity.Mathematics.float4 curvePosition, Game.Vehicles.TrainLaneFlags laneFlags)`  
- `public TrainBogieLane(Game.Vehicles.TrainNavigationLane navLane)`  
- `public TrainBogieLane(Game.Pathfind.PathElement pathElement)`  
- `public TrainBogieLane(Unity.Entities.Entity lane, System.Single curvePosition)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

