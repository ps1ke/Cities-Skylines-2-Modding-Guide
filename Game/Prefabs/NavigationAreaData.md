# Game.Prefabs.NavigationAreaData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct NavigationAreaData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.RouteConnectionType m_ConnectionType;
    public Game.Prefabs.RouteConnectionType m_SecondaryType;
    public Game.Net.TrackTypes m_TrackTypes;
    public Game.Net.RoadTypes m_RoadTypes;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.RouteConnectionType m_ConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_ConnectionType;
```

- `public Game.Prefabs.RouteConnectionType m_SecondaryType`  

```csharp
public Game.Prefabs.RouteConnectionType m_SecondaryType;
```

- `public Game.Net.TrackTypes m_TrackTypes`  

```csharp
public Game.Net.TrackTypes m_TrackTypes;
```

- `public Game.Net.RoadTypes m_RoadTypes`  

```csharp
public Game.Net.RoadTypes m_RoadTypes;
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


