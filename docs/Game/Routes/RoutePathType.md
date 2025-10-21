# Game.Routes.RoutePathSystem+RoutePathType

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Routes.RoutePathSystem+RoutePathType>`  

## Code

```csharp
public sealed struct RoutePathType : System.IEquatable<Game.Routes.RoutePathSystem+RoutePathType>
{
    public Game.Prefabs.RouteConnectionType m_ConnectionType;
    public Game.Net.RoadTypes m_RoadType;
    public Game.Net.TrackTypes m_TrackType;

    public System.Boolean Equals(Game.Routes.RoutePathSystem+RoutePathType other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Game.Prefabs.RouteConnectionType m_ConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_ConnectionType;
```

- `public Game.Net.RoadTypes m_RoadType`  

```csharp
public Game.Net.RoadTypes m_RoadType;
```

- `public Game.Net.TrackTypes m_TrackType`  

```csharp
public Game.Net.TrackTypes m_TrackType;
```


## Methods

- `public Equals(Game.Routes.RoutePathSystem+RoutePathType other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Routes.RoutePathSystem+RoutePathType other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


