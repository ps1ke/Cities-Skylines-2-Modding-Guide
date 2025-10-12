# Game.Prefabs.MeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  
- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, System.Int32> m_MaterialIndex`  
- `private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey`  
- `private Game.Prefabs.MeshSystem+TypeHandle __TypeHandle`  

## Constructors

- `public MeshSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetMaterialIndex(Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.MeshSystem+RemoveBatchGroupsJob`  
- `Game.Prefabs.MeshSystem+InitializeMeshJob`  
- `Game.Prefabs.MeshSystem+TypeHandle`  

