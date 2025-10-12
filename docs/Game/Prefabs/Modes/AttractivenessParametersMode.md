# Game.Prefabs.Modes.AttractivenessParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_ForestEffect`  
- `public System.Single m_ForestDistance`  
- `public System.Single m_ShoreEffect`  
- `public System.Single m_ShoreDistance`  
- `public Unity.Mathematics.float3 m_HeightBonus`  
- `public Unity.Mathematics.float2 m_AttractiveTemperature`  
- `public Unity.Mathematics.float2 m_ExtremeTemperature`  
- `public Unity.Mathematics.float2 m_TemperatureAffect`  
- `public Unity.Mathematics.float2 m_RainEffectRange`  
- `public Unity.Mathematics.float2 m_SnowEffectRange`  
- `public Unity.Mathematics.float3 m_SnowRainExtremeAffect`  

## Constructors

- `public AttractivenessParametersMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

