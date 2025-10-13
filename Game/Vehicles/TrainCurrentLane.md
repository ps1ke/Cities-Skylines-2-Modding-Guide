# Game.Vehicles.TrainCurrentLane

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrainCurrentLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.TrainBogieLane m_Front;
    public Game.Vehicles.TrainBogieLane m_Rear;
    public Game.Vehicles.TrainBogieCache m_FrontCache;
    public Game.Vehicles.TrainBogieCache m_RearCache;
    public System.Single m_Duration;
    public System.Single m_Distance;

    public TrainCurrentLane(Game.Pathfind.PathElement pathElement);
    public TrainCurrentLane(Game.Vehicles.ParkedTrain parkedTrain);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.TrainBogieLane m_Front`  

```csharp
public Game.Vehicles.TrainBogieLane m_Front;
```

- `public Game.Vehicles.TrainBogieLane m_Rear`  

```csharp
public Game.Vehicles.TrainBogieLane m_Rear;
```

- `public Game.Vehicles.TrainBogieCache m_FrontCache`  

```csharp
public Game.Vehicles.TrainBogieCache m_FrontCache;
```

- `public Game.Vehicles.TrainBogieCache m_RearCache`  

```csharp
public Game.Vehicles.TrainBogieCache m_RearCache;
```

- `public System.Single m_Duration`  

```csharp
public System.Single m_Duration;
```

- `public System.Single m_Distance`  

```csharp
public System.Single m_Distance;
```


## Constructors

- `public TrainCurrentLane(Game.Pathfind.PathElement pathElement)`  

```csharp
public TrainCurrentLane(ParkedTrain parkedTrain)
	{
		m_Front = new TrainBogieLane(parkedTrain.m_FrontLane, parkedTrain.m_CurvePosition.x);
		m_Rear = new TrainBogieLane(parkedTrain.m_RearLane, parkedTrain.m_CurvePosition.y);
		m_FrontCache = new TrainBogieCache(parkedTrain.m_FrontLane, parkedTrain.m_CurvePosition.x);
		m_RearCache = new TrainBogieCache(parkedTrain.m_RearLane, parkedTrain.m_CurvePosition.y);
		m_Duration = 0f;
		m_Distance = 0f;
	}
```

- `public TrainCurrentLane(Game.Vehicles.ParkedTrain parkedTrain)`  

```csharp
public TrainCurrentLane(ParkedTrain parkedTrain)
	{
		m_Front = new TrainBogieLane(parkedTrain.m_FrontLane, parkedTrain.m_CurvePosition.x);
		m_Rear = new TrainBogieLane(parkedTrain.m_RearLane, parkedTrain.m_CurvePosition.y);
		m_FrontCache = new TrainBogieCache(parkedTrain.m_FrontLane, parkedTrain.m_CurvePosition.x);
		m_RearCache = new TrainBogieCache(parkedTrain.m_RearLane, parkedTrain.m_CurvePosition.y);
		m_Duration = 0f;
		m_Distance = 0f;
	}
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


