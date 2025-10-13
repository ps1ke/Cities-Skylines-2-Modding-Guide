# Game.Vehicles.TrainBogieLane

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrainBogieLane : Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Mathematics.float4 m_CurvePosition;
    public Game.Vehicles.TrainLaneFlags m_LaneFlags;

    public TrainBogieLane(Game.Vehicles.TrainBogieCache cache);
    public TrainBogieLane(Unity.Entities.Entity lane, Unity.Mathematics.float4 curvePosition, Game.Vehicles.TrainLaneFlags laneFlags);
    public TrainBogieLane(Game.Vehicles.TrainNavigationLane navLane);
    public TrainBogieLane(Game.Pathfind.PathElement pathElement);
    public TrainBogieLane(Unity.Entities.Entity lane, System.Single curvePosition);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Mathematics.float4 m_CurvePosition`  

```csharp
public Unity.Mathematics.float4 m_CurvePosition;
```

- `public Game.Vehicles.TrainLaneFlags m_LaneFlags`  

```csharp
public Game.Vehicles.TrainLaneFlags m_LaneFlags;
```


## Constructors

- `public TrainBogieLane(Game.Vehicles.TrainBogieCache cache)`  

```csharp
public TrainBogieLane(Entity lane, float curvePosition)
	{
		m_Lane = lane;
		m_CurvePosition = curvePosition;
		m_LaneFlags = (TrainLaneFlags)0u;
	}
```

- `public TrainBogieLane(Unity.Entities.Entity lane, Unity.Mathematics.float4 curvePosition, Game.Vehicles.TrainLaneFlags laneFlags)`  

```csharp
public TrainBogieLane(Entity lane, float curvePosition)
	{
		m_Lane = lane;
		m_CurvePosition = curvePosition;
		m_LaneFlags = (TrainLaneFlags)0u;
	}
```

- `public TrainBogieLane(Game.Vehicles.TrainNavigationLane navLane)`  

```csharp
public TrainBogieLane(Entity lane, float curvePosition)
	{
		m_Lane = lane;
		m_CurvePosition = curvePosition;
		m_LaneFlags = (TrainLaneFlags)0u;
	}
```

- `public TrainBogieLane(Game.Pathfind.PathElement pathElement)`  

```csharp
public TrainBogieLane(Entity lane, float curvePosition)
	{
		m_Lane = lane;
		m_CurvePosition = curvePosition;
		m_LaneFlags = (TrainLaneFlags)0u;
	}
```

- `public TrainBogieLane(Unity.Entities.Entity lane, System.Single curvePosition)`  

```csharp
public TrainBogieLane(Entity lane, float curvePosition)
	{
		m_Lane = lane;
		m_CurvePosition = curvePosition;
		m_LaneFlags = (TrainLaneFlags)0u;
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


