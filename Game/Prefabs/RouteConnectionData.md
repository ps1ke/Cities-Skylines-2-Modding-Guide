# Game.Prefabs.RouteConnectionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct RouteConnectionData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.RouteConnectionType m_AccessConnectionType;
    public Game.Prefabs.RouteConnectionType m_RouteConnectionType;
    public Game.Net.TrackTypes m_AccessTrackType;
    public Game.Net.TrackTypes m_RouteTrackType;
    public Game.Net.RoadTypes m_AccessRoadType;
    public Game.Net.RoadTypes m_RouteRoadType;
    public Game.Vehicles.SizeClass m_RouteSizeClass;
    public System.Single m_StartLaneOffset;
    public System.Single m_EndMargin;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.RouteConnectionType m_AccessConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_AccessConnectionType;
```

- `public Game.Prefabs.RouteConnectionType m_RouteConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_RouteConnectionType;
```

- `public Game.Net.TrackTypes m_AccessTrackType`  

```csharp
public Game.Net.TrackTypes m_AccessTrackType;
```

- `public Game.Net.TrackTypes m_RouteTrackType`  

```csharp
public Game.Net.TrackTypes m_RouteTrackType;
```

- `public Game.Net.RoadTypes m_AccessRoadType`  

```csharp
public Game.Net.RoadTypes m_AccessRoadType;
```

- `public Game.Net.RoadTypes m_RouteRoadType`  

```csharp
public Game.Net.RoadTypes m_RouteRoadType;
```

- `public Game.Vehicles.SizeClass m_RouteSizeClass`  

```csharp
public Game.Vehicles.SizeClass m_RouteSizeClass;
```

- `public System.Single m_StartLaneOffset`  

```csharp
public System.Single m_StartLaneOffset;
```

- `public System.Single m_EndMargin`  

```csharp
public System.Single m_EndMargin;
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


