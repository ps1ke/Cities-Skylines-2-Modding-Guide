# Game.Vehicles.ParkedTrain

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ParkedTrain : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_ParkingLocation;
    public Unity.Entities.Entity m_FrontLane;
    public Unity.Entities.Entity m_RearLane;
    public Unity.Mathematics.float2 m_CurvePosition;

    public ParkedTrain(Unity.Entities.Entity location);
    public ParkedTrain(Unity.Entities.Entity location, Game.Vehicles.TrainCurrentLane currentLane);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_ParkingLocation`  

```csharp
public Unity.Entities.Entity m_ParkingLocation;
```

- `public Unity.Entities.Entity m_FrontLane`  

```csharp
public Unity.Entities.Entity m_FrontLane;
```

- `public Unity.Entities.Entity m_RearLane`  

```csharp
public Unity.Entities.Entity m_RearLane;
```

- `public Unity.Mathematics.float2 m_CurvePosition`  

```csharp
public Unity.Mathematics.float2 m_CurvePosition;
```


## Constructors

- `public ParkedTrain(Unity.Entities.Entity location)`  

```csharp
public ParkedTrain(Unity.Entities.Entity location);
```

- `public ParkedTrain(Unity.Entities.Entity location, Game.Vehicles.TrainCurrentLane currentLane)`  

```csharp
public ParkedTrain(Unity.Entities.Entity location, Game.Vehicles.TrainCurrentLane currentLane);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


