# Game.Net.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <netsUpdated>k__BackingField`  
- `private System.Boolean <lanesUpdated>k__BackingField`  
- `private Unity.Entities.EntityQuery m_NetGeometryQuery`  
- `private Unity.Entities.EntityQuery m_LaneGeometryQuery`  
- `private Game.Net.SearchSystem m_SearchSystem`  
- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedNetBounds`  
- `private Unity.Jobs.JobHandle m_NetWriteDependencies`  
- `private Unity.Jobs.JobHandle m_NetReadDependencies`  
- `private Unity.Jobs.JobHandle m_LaneWriteDependencies`  
- `private Unity.Jobs.JobHandle m_LaneReadDependencies`  
- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedLaneBounds`  
- `private Game.Net.UpdateCollectSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean netsUpdated { get; private set }`  
- `public System.Boolean lanesUpdated { get; private set }`  

## Constructors

- `public UpdateCollectSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddLaneBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddNetBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public GetUpdatedLaneBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  
- `public GetUpdatedNetBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.UpdateCollectSystem+CollectUpdatedNetBoundsJob`  
- `Game.Net.UpdateCollectSystem+CollectUpdatedLaneBoundsJob`  
- `Game.Net.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Net.UpdateCollectSystem+TypeHandle`  

