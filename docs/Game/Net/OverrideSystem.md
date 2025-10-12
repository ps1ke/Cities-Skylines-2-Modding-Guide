# Game.Net.OverrideSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Net.OverrideSystem+TypeHandle __TypeHandle`  
- `private static const System.Single MIN_PARALLEL_FENCE_DISTANCE`  

## Constructors

- `public OverrideSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CollectUpdatedLanes(Unity.Collections.NativeList<Unity.Entities.Entity> updateLanesList) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.OverrideSystem+TreeAction`  
- `Game.Net.OverrideSystem+UpdateOverriddenLayersJob`  
- `Game.Net.OverrideSystem+FindUpdatedLanesJob`  
- `Game.Net.OverrideSystem+CollectObjectsJob`  
- `Game.Net.OverrideSystem+CheckLaneOverrideJob`  
- `Game.Net.OverrideSystem+TypeHandle`  

