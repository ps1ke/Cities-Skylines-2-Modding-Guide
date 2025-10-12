# Game.Prefabs.PrefabInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.PrefabInitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PrefabInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private InitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.Queue<Game.Prefabs.PrefabInitializeSystem+QueueItem> queue, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabSet, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Void`  
- `private LateInitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.PrefabInitializeSystem+ListItem`  
- `Game.Prefabs.PrefabInitializeSystem+QueueItem`  
- `Game.Prefabs.PrefabInitializeSystem+TypeHandle`  

