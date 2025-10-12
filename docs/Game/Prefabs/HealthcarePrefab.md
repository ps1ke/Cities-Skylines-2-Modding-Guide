# Game.Prefabs.HealthcarePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.PrefabBase m_HealthcareServicePrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_AmbulanceNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_HearseNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_FacilityFullNotificationPrefab`  
- `public System.Single m_TransportWarningTime`  
- `public System.Single m_NoResourceTreatmentPenalty`  
- `public System.Single m_BuildingDestoryDeathRate`  
- `public UnityEngine.AnimationCurve m_DeathRate`  

## Constructors

- `public HealthcarePrefab()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

