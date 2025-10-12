# Game.Prefabs.ReplacePrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.ReplacePrefabSystem+Finalize m_FinalizeSystem`  
- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  
- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_PrefabRefQuery`  
- `private Unity.Entities.Entity m_OldPrefab`  
- `private Unity.Entities.Entity m_NewPrefab`  
- `private Unity.Entities.Entity m_SourceInstance`  
- `private Unity.Collections.NativeList<Game.Prefabs.ReplacePrefabSystem+ReplaceMesh> m_MeshReplaces`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdateInstances`  
- `private Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData> m_ReplacePrefabData`  
- `private Game.Prefabs.ReplacePrefabSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ReplacePrefabSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CheckInstanceComponents(Unity.Entities.Entity instance, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> checkedComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> archetypeComponents) : System.Void`  
- `public FinalizeReplaces() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public ReplacePrefab(Unity.Entities.Entity oldPrefab, Unity.Entities.Entity newPrefab, Unity.Entities.Entity sourceInstance) : System.Void`  

## Nested types

- `Game.Prefabs.ReplacePrefabSystem+ReplaceMesh`  
- `Game.Prefabs.ReplacePrefabSystem+ReplacePrefabData`  
- `Game.Prefabs.ReplacePrefabSystem+Finalize`  
- `Game.Prefabs.ReplacePrefabSystem+RemoveBatchGroupsJob`  
- `Game.Prefabs.ReplacePrefabSystem+ReplacePrefabJob`  
- `Game.Prefabs.ReplacePrefabSystem+TypeHandle`  

