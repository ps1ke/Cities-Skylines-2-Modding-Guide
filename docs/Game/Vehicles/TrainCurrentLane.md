# Game.Vehicles.TrainCurrentLane

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Vehicles.TrainBogieLane m_Front`  
- `public Game.Vehicles.TrainBogieLane m_Rear`  
- `public Game.Vehicles.TrainBogieCache m_FrontCache`  
- `public Game.Vehicles.TrainBogieCache m_RearCache`  
- `public System.Single m_Duration`  
- `public System.Single m_Distance`  

## Constructors

- `public TrainCurrentLane(Game.Pathfind.PathElement pathElement)`  
- `public TrainCurrentLane(Game.Vehicles.ParkedTrain parkedTrain)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

