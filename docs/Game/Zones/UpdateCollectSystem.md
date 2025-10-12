# Game.Zones.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <isUpdated>k__BackingField`  
- `private Unity.Entities.EntityQuery m_BlockQuery`  
- `private Game.Zones.SearchSystem m_SearchSystem`  
- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedBounds`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Game.Zones.UpdateCollectSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean isUpdated { get; private set }`  

## Constructors

- `public UpdateCollectSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddBoundsWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public GetUpdatedBounds(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Zones.UpdateCollectSystem+CollectUpdatedBlockBoundsJob`  
- `Game.Zones.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Zones.UpdateCollectSystem+TypeHandle`  

