# Game.Net.OutsideConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Unity.Entities.EntityQuery m_ConnectionQuery`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private System.Boolean m_Regenerate`  
- `private Game.Net.OutsideConnectionSystem+TypeHandle __TypeHandle`  

## Constructors

- `public OutsideConnectionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context context) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.OutsideConnectionSystem+ConnectionType`  
- `Game.Net.OutsideConnectionSystem+NodeData`  
- `Game.Net.OutsideConnectionSystem+LaneData`  
- `Game.Net.OutsideConnectionSystem+UpdateOutsideConnectionsJob`  
- `Game.Net.OutsideConnectionSystem+TypeHandle`  

