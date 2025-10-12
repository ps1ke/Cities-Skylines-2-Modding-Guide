# Game.Vehicles.TrainBogieCache

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Lane`  
- `public Unity.Mathematics.float2 m_CurvePosition`  
- `public Game.Vehicles.TrainLaneFlags m_LaneFlags`  

## Constructors

- `public TrainBogieCache(Game.Vehicles.TrainBogieLane lane)`  
- `public TrainBogieCache(Game.Pathfind.PathElement pathElement)`  
- `public TrainBogieCache(Unity.Entities.Entity lane, System.Single curvePosition)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

