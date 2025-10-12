# Game.Vehicles.ParkedTrain

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_ParkingLocation`  
- `public Unity.Entities.Entity m_FrontLane`  
- `public Unity.Entities.Entity m_RearLane`  
- `public Unity.Mathematics.float2 m_CurvePosition`  

## Constructors

- `public ParkedTrain(Unity.Entities.Entity location)`  
- `public ParkedTrain(Unity.Entities.Entity location, Game.Vehicles.TrainCurrentLane currentLane)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

