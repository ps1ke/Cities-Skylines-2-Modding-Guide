# Game.Prefabs.FireConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.NotificationIconPrefab m_FireNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_BurnedDownNotificationPrefab`  
- `public System.Single m_DefaultStructuralIntegrity`  
- `public System.Single m_BuildingStructuralIntegrity`  
- `public System.Single m_StructuralIntegrityLevel1`  
- `public System.Single m_StructuralIntegrityLevel2`  
- `public System.Single m_StructuralIntegrityLevel3`  
- `public System.Single m_StructuralIntegrityLevel4`  
- `public System.Single m_StructuralIntegrityLevel5`  
- `public Colossal.Mathematics.Bounds1 m_ResponseTimeRange`  
- `public System.Single m_TelecomResponseTimeModifier`  
- `public System.Single m_DarknessResponseTimeModifier`  
- `public UnityEngine.AnimationCurve m_TemperatureForestFireHazard`  
- `public UnityEngine.AnimationCurve m_NoRainForestFireHazard`  
- `public System.Single m_DeathRateOfFireAccident`  

## Constructors

- `public FireConfigurationPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

