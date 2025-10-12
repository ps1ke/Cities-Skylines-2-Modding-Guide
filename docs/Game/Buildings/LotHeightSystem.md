# Game.Buildings.LotHeightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  
- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_UpdateQuery`  
- `private Unity.Entities.EntityQuery m_AllQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Buildings.LotHeightSystem+TypeHandle __TypeHandle`  

## Constructors

- `public LotHeightSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Buildings.LotHeightSystem+AddUpdatedLotsJob`  
- `Game.Buildings.LotHeightSystem+FindUpdatedLotsJob`  
- `Game.Buildings.LotHeightSystem+CollectLotsJob`  
- `Game.Buildings.LotHeightSystem+Heights`  
- `Game.Buildings.LotHeightSystem+UpdateLotHeightsJob`  
- `Game.Buildings.LotHeightSystem+TypeHandle`  

