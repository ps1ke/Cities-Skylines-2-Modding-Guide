# Game.Prefabs.StatisticTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.StatisticTriggerType m_Type`  
- `public Game.Prefabs.StatisticsPrefab m_StatisticPrefab`  
- `public System.Int32 m_StatisticParameter`  
- `public Game.Prefabs.StatisticsPrefab m_NormalizeWithPrefab`  
- `public System.Int32 m_NormalizeWithParameter`  
- `public System.Int32 m_TimeFrame`  
- `public System.Int32 m_MinSamples`  

## Constructors

- `public StatisticTriggerPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

