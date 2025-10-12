# Game.Areas.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Areas.SearchSystem m_SearchSystem`  
- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_LotData`  
- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_DistrictData`  
- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_MapTileData`  
- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_SpaceData`  
- `private Game.Areas.UpdateCollectSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean lotsUpdated { get }`  
- `public System.Boolean districtsUpdated { get }`  
- `public System.Boolean mapTilesUpdated { get }`  
- `public System.Boolean spacesUpdated { get }`  

## Constructors

- `public UpdateCollectSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddDistrictBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddLotBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddMapTileBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddSpaceBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `private GetQuery<T>() : Unity.Entities.EntityQuery`  
- `public GetUpdatedDistrictBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  
- `public GetUpdatedLotBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  
- `public GetUpdatedMapTileBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  
- `public GetUpdatedSpaceBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UpdateBounds(Game.Areas.UpdateCollectSystem+UpdateBufferData& data, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Areas.UpdateCollectSystem+UpdateBufferData`  
- `Game.Areas.UpdateCollectSystem+CollectUpdatedAreaBoundsJob`  
- `Game.Areas.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Areas.UpdateCollectSystem+TypeHandle`  

