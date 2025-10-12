# Game.Prefabs.DisasterConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.NotificationIconPrefab m_WeatherDamageNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_WeatherDestroyedNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_WaterDamageNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_WaterDestroyedNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_DestroyedNotificationPrefab`  
- `public System.Single m_FloodDamageRate`  
- `public UnityEngine.AnimationCurve m_EmergencyShelterDangerLevelExitProbability`  
- `public System.Single m_InoperableEmergencyShelterExitProbability`  

## Constructors

- `public DisasterConfigurationPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

