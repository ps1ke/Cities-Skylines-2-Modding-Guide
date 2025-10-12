# Game.Prefabs.NetCompositionMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_MeshQuery`  
- `private Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> m_MeshEntities`  
- `private Unity.Jobs.JobHandle m_Dependencies`  
- `private Game.Prefabs.NetCompositionMeshSystem+TypeHandle __TypeHandle`  

## Constructors

- `public NetCompositionMeshSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddMeshEntityReader(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public GetMeshEntities(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.NetCompositionMeshSystem+CompositionMeshJob`  
- `Game.Prefabs.NetCompositionMeshSystem+TypeHandle`  

