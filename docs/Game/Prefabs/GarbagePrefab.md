# Game.Prefabs.GarbagePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.ServicePrefab m_GarbageServicePrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_GarbageNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_FacilityFullNotificationPrefab`  
- `public System.Int32 m_HomelessGarbageProduce`  
- `public System.Int32 m_CollectionGarbageLimit`  
- `public System.Int32 m_RequestGarbageLimit`  
- `public System.Int32 m_WarningGarbageLimit`  
- `public System.Int32 m_MaxGarbageAccumulation`  
- `public System.Single m_BuildingLevelBalance`  
- `public System.Single m_EducationBalance`  
- `public System.Int32 m_HappinessEffectBaseline`  
- `public System.Int32 m_HappinessEffectStep`  

## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `public GarbagePrefab()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

