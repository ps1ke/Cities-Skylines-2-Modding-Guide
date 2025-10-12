# Game.Net.NetComponentsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_UpdatedNetQuery`  
- `private Unity.Entities.EntityQuery m_AllNetQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Net.NetComponentsSystem+TypeHandle __TypeHandle`  

## Constructors

- `public NetComponentsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.NetComponentsSystem+CheckNodeComponentsJob`  
- `Game.Net.NetComponentsSystem+TypeHandle`  

