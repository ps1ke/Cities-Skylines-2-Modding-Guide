# Game.Objects.OverrideSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  
- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  
- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Unity.Entities.ComponentTypeSet m_OverriddenUpdatedSet`  
- `private Game.Objects.OverrideSystem+TypeHandle __TypeHandle`  

## Constructors

- `public OverrideSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CollectUpdatedObjects(Unity.Collections.NativeList<Unity.Entities.Entity> updateObjectsList, Unity.Collections.NativeHashSet<Unity.Entities.Entity> objectSet) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Objects.OverrideSystem+TreeAction`  
- `Game.Objects.OverrideSystem+OverridableAction`  
- `Game.Objects.OverrideSystem+UpdateObjectOverrideJob`  
- `Game.Objects.OverrideSystem+FindUpdatedObjectsJob`  
- `Game.Objects.OverrideSystem+CollectObjectsJob`  
- `Game.Objects.OverrideSystem+CheckObjectOverrideJob`  
- `Game.Objects.OverrideSystem+TypeHandle`  

