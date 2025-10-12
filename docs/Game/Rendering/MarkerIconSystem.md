# Game.Rendering.MarkerIconSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.Entity m_SelectedMarker`  
- `private Unity.Entities.Entity m_FollowedMarker`  
- `private Unity.Entities.Entity m_SelectedLocation`  
- `private Unity.Entities.Entity m_FollowedLocation`  
- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  
- `private Unity.Entities.EntityQuery m_IconQuery`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Rendering.MarkerIconSystem+TypeHandle __TypeHandle`  

## Constructors

- `public MarkerIconSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AdjustLocations(Unity.Mathematics.float3 selectedLocation, Unity.Mathematics.float3 followedLocation, Unity.Mathematics.float3 cameraPos, Unity.Mathematics.float3 cameraUp) : System.Void`  
- `private CreateMarker(Unity.Entities.Entity target, Unity.Mathematics.float3 position, Game.Rendering.MarkerIconSystem+MarkerType markerType, System.Boolean skipAnimation) : Unity.Entities.Entity`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RemoveMarker(Unity.Entities.Entity& marker, System.Boolean skipAnimation) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdateMarker(Unity.Entities.Entity& marker, Unity.Entities.Entity target, Game.Rendering.MarkerIconSystem+MarkerType markerType, Unity.Mathematics.float3 position, System.Boolean skipAnimation) : System.Void`  

## Nested types

- `Game.Rendering.MarkerIconSystem+MarkerType`  
- `Game.Rendering.MarkerIconSystem+Overlap`  
- `Game.Rendering.MarkerIconSystem+FindOverlapIconsJob`  
- `Game.Rendering.MarkerIconSystem+UpdateMarkerLocationJob`  
- `Game.Rendering.MarkerIconSystem+TypeHandle`  

