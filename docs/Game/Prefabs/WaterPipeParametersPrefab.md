# Game.Prefabs.WaterPipeParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.PrefabBase m_WaterService`  
- `public Game.Prefabs.NotificationIconPrefab m_WaterNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_DirtyWaterNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_SewageNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_WaterPipeNotConnectedNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_SewagePipeNotConnectedNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughWaterCapacityNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughSewageCapacityNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughGroundwaterNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughSurfaceWaterNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_DirtyWaterPumpNotification`  
- `public System.Single m_GroundwaterReplenish`  
- `public System.Int32 m_GroundwaterPurification`  
- `public System.Single m_GroundwaterUsageMultiplier`  
- `public System.Single m_GroundwaterPumpEffectiveAmount`  
- `public System.Single m_SurfaceWaterUsageMultiplier`  
- `public System.Single m_SurfaceWaterPumpEffectiveDepth`  
- `public System.Single m_MaxToleratedPollution`  
- `public System.Int32 m_WaterPipePollutionSpreadInterval`  
- `public System.Single m_StaleWaterPipePurification`  

## Constructors

- `public WaterPipeParametersPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

