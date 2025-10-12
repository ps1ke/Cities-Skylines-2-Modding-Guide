# Game.Vehicles.CarTrailerLane

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Lane`  
- `public Unity.Entities.Entity m_NextLane`  
- `public Unity.Mathematics.float2 m_CurvePosition`  
- `public Unity.Mathematics.float2 m_NextPosition`  
- `public System.Single m_Duration`  
- `public System.Single m_Distance`  

## Constructors

- `public CarTrailerLane(Game.Vehicles.ParkedCar parkedCar)`  
- `public CarTrailerLane(Game.Vehicles.CarCurrentLane currentLane)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

