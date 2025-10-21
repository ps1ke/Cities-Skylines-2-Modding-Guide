# Game.Vehicles.WatercraftCurrentLane

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WatercraftCurrentLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Entities.Entity m_ChangeLane;
    public Unity.Mathematics.float3 m_CurvePosition;
    public Game.Vehicles.WatercraftLaneFlags m_LaneFlags;
    public System.Single m_ChangeProgress;
    public System.Single m_Duration;
    public System.Single m_Distance;
    public System.Single m_LanePosition;

    public WatercraftCurrentLane(Game.Pathfind.PathElement pathElement, Game.Vehicles.WatercraftLaneFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Entities.Entity m_ChangeLane`  

```csharp
public Unity.Entities.Entity m_ChangeLane;
```

- `public Unity.Mathematics.float3 m_CurvePosition`  

```csharp
public Unity.Mathematics.float3 m_CurvePosition;
```

- `public Game.Vehicles.WatercraftLaneFlags m_LaneFlags`  

```csharp
public Game.Vehicles.WatercraftLaneFlags m_LaneFlags;
```

- `public System.Single m_ChangeProgress`  

```csharp
public System.Single m_ChangeProgress;
```

- `public System.Single m_Duration`  

```csharp
public System.Single m_Duration;
```

- `public System.Single m_Distance`  

```csharp
public System.Single m_Distance;
```

- `public System.Single m_LanePosition`  

```csharp
public System.Single m_LanePosition;
```


## Constructors

- `public WatercraftCurrentLane(Game.Pathfind.PathElement pathElement, Game.Vehicles.WatercraftLaneFlags flags)`  

```csharp
public WatercraftCurrentLane(Game.Pathfind.PathElement pathElement, Game.Vehicles.WatercraftLaneFlags flags);
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


