# Game.Prefabs.TransportLinePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RoutePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColored`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportLinePrefab : Game.Prefabs.RoutePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IColored
{
    public Game.Prefabs.RouteConnectionType m_AccessConnectionType;
    public Game.Prefabs.RouteConnectionType m_RouteConnectionType;
    public Game.Net.TrackTypes m_AccessTrackType;
    public Game.Net.TrackTypes m_RouteTrackType;
    public Game.Net.RoadTypes m_AccessRoadType;
    public Game.Net.RoadTypes m_RouteRoadType;
    public Game.Prefabs.TransportType m_TransportType;
    public System.Single m_DefaultVehicleInterval;
    public System.Single m_DefaultUnbunchingFactor;
    public System.Single m_StopDuration;
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Boolean m_PassengerTransport;
    public System.Boolean m_CargoTransport;
    public Game.Prefabs.PathfindPrefab m_PathfindPrefab;
    public Game.Prefabs.NotificationIconPrefab m_VehicleNotification;

    public TransportLinePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
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

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public System.Single m_DefaultVehicleInterval`  

```csharp
public System.Single m_DefaultVehicleInterval;
```

- `public System.Single m_DefaultUnbunchingFactor`  

```csharp
public System.Single m_DefaultUnbunchingFactor;
```

- `public System.Single m_StopDuration`  

```csharp
public System.Single m_StopDuration;
```

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Boolean m_PassengerTransport`  

```csharp
public System.Boolean m_PassengerTransport;
```

- `public System.Boolean m_CargoTransport`  

```csharp
public System.Boolean m_CargoTransport;
```

- `public Game.Prefabs.PathfindPrefab m_PathfindPrefab`  

```csharp
public Game.Prefabs.PathfindPrefab m_PathfindPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_VehicleNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_VehicleNotification;
```


## Constructors

- `public TransportLinePrefab()`  

```csharp
public TransportLinePrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


