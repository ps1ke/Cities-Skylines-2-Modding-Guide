# Game.Prefabs.TransportLinePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RoutePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColored`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.RouteConnectionType m_AccessConnectionType`  
- `public Game.Prefabs.RouteConnectionType m_RouteConnectionType`  
- `public Game.Net.TrackTypes m_AccessTrackType`  
- `public Game.Net.TrackTypes m_RouteTrackType`  
- `public Game.Net.RoadTypes m_AccessRoadType`  
- `public Game.Net.RoadTypes m_RouteRoadType`  
- `public Game.Prefabs.TransportType m_TransportType`  
- `public System.Single m_DefaultVehicleInterval`  
- `public System.Single m_DefaultUnbunchingFactor`  
- `public System.Single m_StopDuration`  
- `public Game.Vehicles.SizeClass m_SizeClass`  
- `public System.Boolean m_PassengerTransport`  
- `public System.Boolean m_CargoTransport`  
- `public Game.Prefabs.PathfindPrefab m_PathfindPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_VehicleNotification`  

## Constructors

- `public TransportLinePrefab()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

