# Game.Prefabs.Modes.EntityQueryModePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.Modes.ModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Constructors

- `protected EntityQueryModePrefab()`  

## Methods

- `public abstract ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public abstract GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `public RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities) : System.Void`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public abstract RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  
- `public virtual StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& requestedQuery, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

