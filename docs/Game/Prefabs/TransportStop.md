# Game.Prefabs.TransportStop

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.TransportType m_TransportType`  
- `public Game.Prefabs.RouteConnectionType m_AccessConnectionType`  
- `public Game.Prefabs.RouteConnectionType m_RouteConnectionType`  
- `public Game.Net.TrackTypes m_AccessTrackType`  
- `public Game.Net.TrackTypes m_RouteTrackType`  
- `public Game.Net.RoadTypes m_AccessRoadType`  
- `public Game.Net.RoadTypes m_RouteRoadType`  
- `public System.Single m_EnterDistance`  
- `public System.Single m_ExitDistance`  
- `public System.Single m_AccessDistance`  
- `public System.Single m_BoardingTime`  
- `public System.Single m_ComfortFactor`  
- `public System.Single m_LoadingFactor`  
- `public System.Boolean m_PassengerTransport`  
- `public System.Boolean m_CargoTransport`  

## Constructors

- `public TransportStop()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

