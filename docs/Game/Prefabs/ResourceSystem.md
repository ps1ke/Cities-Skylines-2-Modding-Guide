# Game.Prefabs.ResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_PrefabGroup`  
- `private Unity.Entities.EntityQuery m_InfoGroup`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourcePrefabs`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourceInfos`  
- `private Unity.Jobs.JobHandle m_PrefabsReaders`  
- `private System.Int32 m_BaseConsumptionSum`  
- `private Game.Prefabs.ResourceSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Int32 BaseConsumptionSum { get }`  

## Constructors

- `public ResourceSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddPrefabsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public GetPrefab(Game.Economy.Resource resource) : Unity.Entities.Entity`  
- `public GetPrefabs() : Game.Prefabs.ResourcePrefabs`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.ResourceSystem+TypeHandle`  

