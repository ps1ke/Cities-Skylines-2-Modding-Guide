# Game.Serialization.CheckPrefabReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray`  
- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs`  
- `private Unity.Jobs.JobHandle m_DataDeps`  
- `private Unity.Jobs.JobHandle m_UserDeps`  
- `private System.Boolean m_IsLoading`  

## Constructors

- `public CheckPrefabReferencesSystem()`  

## Methods

- `public AddPrefabReferencesUser(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public BeginPrefabCheck(Unity.Collections.NativeArray<Unity.Entities.Entity> array, System.Boolean isLoading, Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public EndPrefabCheck(Unity.Jobs.JobHandle& dependencies) : System.Void`  
- `public GetPrefabReferences(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle& dependencies) : Game.Serialization.PrefabReferences`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Serialization.CheckPrefabReferencesSystem+CheckPrefabReferencesJob`  

