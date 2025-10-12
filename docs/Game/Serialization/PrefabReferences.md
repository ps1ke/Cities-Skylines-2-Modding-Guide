# Game.Serialization.PrefabReferences

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> m_PrefabData`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray`  
- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs`  
- `private Unity.Entities.Entity m_LastPrefabIn`  
- `private Unity.Entities.Entity m_LastPrefabOut`  
- `private System.Boolean m_IsLoading`  

## Constructors

- `public PrefabReferences(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabArray, Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> referencedPrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> prefabData, System.Boolean isLoading)`  

## Methods

- `public Check(Unity.Entities.Entity& prefab) : System.Void`  
- `public Check(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab) : Unity.Entities.Entity`  
- `public SetDirty(Unity.Entities.Entity prefab) : System.Void`  

