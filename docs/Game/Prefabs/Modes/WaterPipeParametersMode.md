# Game.Prefabs.Modes.WaterPipeParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

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

- `public WaterPipeParametersMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

