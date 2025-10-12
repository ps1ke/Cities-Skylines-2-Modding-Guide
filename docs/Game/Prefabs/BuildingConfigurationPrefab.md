# Game.Prefabs.BuildingConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Int32 m_BuildingConditionIncrement`  
- `public System.Int32 m_BuildingConditionDecrement`  
- `public Game.Prefabs.NotificationIconPrefab m_AbandonedCollapsedNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_AbandonedNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_CondemnedNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_LevelUpNotification`  
- `public Game.Prefabs.NotificationIconPrefab m_TurnedOffNotification`  
- `public Game.Prefabs.NetLanePrefab m_ElectricityConnectionLane`  
- `public Game.Prefabs.NetLanePrefab m_SewageConnectionLane`  
- `public Game.Prefabs.NetLanePrefab m_WaterConnectionLane`  
- `public System.UInt32 m_AbandonedDestroyDelay`  
- `public Game.Prefabs.NotificationIconPrefab m_HighRentNotification`  
- `public Game.Prefabs.BrandPrefab m_DefaultRenterBrand`  
- `public Game.Prefabs.AreaPrefab m_ConstructionSurface`  
- `public Game.Prefabs.NetLanePrefab m_ConstructionBorder`  
- `public Game.Prefabs.ObjectPrefab m_ConstructionObject`  
- `public Game.Prefabs.ObjectPrefab m_CollapsedObject`  
- `public Game.Prefabs.EffectPrefab m_CollapseVFX`  
- `public Game.Prefabs.EffectPrefab m_CollapseSFX`  
- `public System.Single m_CollapseSFXDensity`  
- `public Game.Prefabs.AreaPrefab m_CollapsedSurface`  
- `public Game.Prefabs.EffectPrefab m_FireLoopSFX`  
- `public Game.Prefabs.EffectPrefab m_FireSpotSFX`  

## Constructors

- `public BuildingConfigurationPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

