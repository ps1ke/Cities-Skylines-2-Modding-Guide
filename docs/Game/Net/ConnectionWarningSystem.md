# Game.Net.ConnectionWarningSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Unity.Entities.EntityQuery m_UpdateQuery`  
- `private Unity.Entities.EntityQuery m_NewGameQuery`  
- `private Unity.Entities.EntityQuery m_WaterConfigQuery`  
- `private Unity.Entities.EntityQuery m_ElectricityConfigQuery`  
- `private Unity.Entities.EntityQuery m_TrafficConfigQuery`  
- `private System.Boolean m_IsNewGame`  
- `private Game.Net.ConnectionWarningSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ConnectionWarningSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetConfigData<T>(Unity.Entities.EntityQuery query) : T`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.ConnectionWarningSystem+CollectOwnersJob`  
- `Game.Net.ConnectionWarningSystem+CollectOwnersJob2`  
- `Game.Net.ConnectionWarningSystem+PathfindElement`  
- `Game.Net.ConnectionWarningSystem+BufferElement`  
- `Game.Net.ConnectionWarningSystem+Connection`  
- `Game.Net.ConnectionWarningSystem+CheckOwnersJob`  
- `Game.Net.ConnectionWarningSystem+TypeHandle`  

