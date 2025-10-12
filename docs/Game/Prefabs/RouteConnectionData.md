# Game.Prefabs.RouteConnectionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Prefabs.RouteConnectionType m_AccessConnectionType`  
- `public Game.Prefabs.RouteConnectionType m_RouteConnectionType`  
- `public Game.Net.TrackTypes m_AccessTrackType`  
- `public Game.Net.TrackTypes m_RouteTrackType`  
- `public Game.Net.RoadTypes m_AccessRoadType`  
- `public Game.Net.RoadTypes m_RouteRoadType`  
- `public Game.Vehicles.SizeClass m_RouteSizeClass`  
- `public System.Single m_StartLaneOffset`  
- `public System.Single m_EndMargin`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

