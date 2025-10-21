# Game.Vehicles.TrainBogieCache

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrainBogieCache : Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Mathematics.float2 m_CurvePosition;
    public Game.Vehicles.TrainLaneFlags m_LaneFlags;

    public TrainBogieCache(Game.Vehicles.TrainBogieLane lane);
    public TrainBogieCache(Game.Pathfind.PathElement pathElement);
    public TrainBogieCache(Unity.Entities.Entity lane, System.Single curvePosition);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Mathematics.float2 m_CurvePosition`  

```csharp
public Unity.Mathematics.float2 m_CurvePosition;
```

- `public Game.Vehicles.TrainLaneFlags m_LaneFlags`  

```csharp
public Game.Vehicles.TrainLaneFlags m_LaneFlags;
```


## Constructors

- `public TrainBogieCache(Game.Vehicles.TrainBogieLane lane)`  

```csharp
public TrainBogieCache(Game.Vehicles.TrainBogieLane lane);
```

- `public TrainBogieCache(Game.Pathfind.PathElement pathElement)`  

```csharp
public TrainBogieCache(Game.Pathfind.PathElement pathElement);
```

- `public TrainBogieCache(Unity.Entities.Entity lane, System.Single curvePosition)`  

```csharp
public TrainBogieCache(Unity.Entities.Entity lane, System.Single curvePosition);
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


