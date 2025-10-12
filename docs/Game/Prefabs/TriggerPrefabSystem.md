# Game.Prefabs.TriggerPrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.TriggerPrefabData m_PrefabData`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Game.Prefabs.TriggerPrefabSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TriggerPrefabSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public ReadTriggerPrefabData(Unity.Jobs.JobHandle& dependencies) : Game.Prefabs.TriggerPrefabData`  

## Nested types

- `Game.Prefabs.TriggerPrefabSystem+UpdateTriggerPrefabDataJob`  
- `Game.Prefabs.TriggerPrefabSystem+TypeHandle`  

