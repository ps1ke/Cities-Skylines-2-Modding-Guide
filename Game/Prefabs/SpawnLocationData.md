# Game.Prefabs.SpawnLocationData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct SpawnLocationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.RouteConnectionType m_ConnectionType;
    public Game.Prefabs.ActivityMask m_ActivityMask;
    public Game.Net.TrackTypes m_TrackTypes;
    public Game.Net.RoadTypes m_RoadTypes;
    public System.Boolean m_RequireAuthorization;
    public System.Boolean m_HangaroundOnLane;

}
```


## Fields

- `public Game.Prefabs.RouteConnectionType m_ConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_ConnectionType;
```

- `public Game.Prefabs.ActivityMask m_ActivityMask`  

```csharp
public Game.Prefabs.ActivityMask m_ActivityMask;
```

- `public Game.Net.TrackTypes m_TrackTypes`  

```csharp
public Game.Net.TrackTypes m_TrackTypes;
```

- `public Game.Net.RoadTypes m_RoadTypes`  

```csharp
public Game.Net.RoadTypes m_RoadTypes;
```

- `public System.Boolean m_RequireAuthorization`  

```csharp
public System.Boolean m_RequireAuthorization;
```

- `public System.Boolean m_HangaroundOnLane`  

```csharp
public System.Boolean m_HangaroundOnLane;
```


