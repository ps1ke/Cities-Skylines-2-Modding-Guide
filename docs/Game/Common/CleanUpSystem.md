# Game.Common.CleanUpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_DeletedEntities`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_UpdatedEntities`  
- `private Unity.Jobs.JobHandle m_DeletedDeps`  
- `private Unity.Jobs.JobHandle m_UpdatedDeps`  
- `private Unity.Entities.ComponentTypeSet m_UpdateTypes`  

## Constructors

- `public CleanUpSystem()`  

## Methods

- `public AddDeleted(Unity.Collections.NativeList<Unity.Entities.Entity> deletedEntities, Unity.Jobs.JobHandle deletedDeps) : System.Void`  
- `public AddUpdated(Unity.Collections.NativeList<Unity.Entities.Entity> updatedEntities, Unity.Jobs.JobHandle updatedDeps) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

