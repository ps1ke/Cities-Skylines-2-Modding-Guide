# Game.Prefabs.TransportStop

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportStop : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TransportType m_TransportType;
    public Game.Prefabs.RouteConnectionType m_AccessConnectionType;
    public Game.Prefabs.RouteConnectionType m_RouteConnectionType;
    public Game.Net.TrackTypes m_AccessTrackType;
    public Game.Net.TrackTypes m_RouteTrackType;
    public Game.Net.RoadTypes m_AccessRoadType;
    public Game.Net.RoadTypes m_RouteRoadType;
    public System.Single m_EnterDistance;
    public System.Single m_ExitDistance;
    public System.Single m_AccessDistance;
    public System.Single m_BoardingTime;
    public System.Single m_ComfortFactor;
    public System.Single m_LoadingFactor;
    public System.Boolean m_PassengerTransport;
    public System.Boolean m_CargoTransport;

    public TransportStop();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

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

- `public System.Single m_EnterDistance`  

```csharp
public System.Single m_EnterDistance;
```

- `public System.Single m_ExitDistance`  

```csharp
public System.Single m_ExitDistance;
```

- `public System.Single m_AccessDistance`  

```csharp
public System.Single m_AccessDistance;
```

- `public System.Single m_BoardingTime`  

```csharp
public System.Single m_BoardingTime;
```

- `public System.Single m_ComfortFactor`  

```csharp
public System.Single m_ComfortFactor;
```

- `public System.Single m_LoadingFactor`  

```csharp
public System.Single m_LoadingFactor;
```

- `public System.Boolean m_PassengerTransport`  

```csharp
public System.Boolean m_PassengerTransport;
```

- `public System.Boolean m_CargoTransport`  

```csharp
public System.Boolean m_CargoTransport;
```


## Constructors

- `public TransportStop()`  

```csharp
public TransportStop();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


