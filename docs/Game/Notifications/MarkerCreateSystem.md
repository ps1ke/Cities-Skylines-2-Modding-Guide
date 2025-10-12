# Game.Notifications.MarkerCreateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_EntityQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private Unity.Entities.EntityQuery m_IconQuery`  
- `private System.UInt32 m_TransportTypeMask`  
- `private System.UInt32 m_BuildingTypeMask`  
- `private System.UInt32 m_BuildingStatusTypeMask`  
- `private System.UInt32 m_VehicleTypeMask`  
- `private System.UInt32 m_MarkerTypeMask`  
- `private System.Boolean m_Loaded`  
- `private Game.Notifications.MarkerCreateSystem+TypeHandle __TypeHandle`  

## Constructors

- `public MarkerCreateSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Notifications.MarkerCreateSystem+MarkerCreateJob`  
- `Game.Notifications.MarkerCreateSystem+TypeHandle`  

