# Game.Prefabs.Modes.ZonePreferenceMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_ResidentialSignificanceServices`  
- `public System.Single m_ResidentialSignificanceWorkplaces`  
- `public System.Single m_ResidentialSignificanceLandValue`  
- `public System.Single m_ResidentialSignificancePollution`  
- `public System.Single m_ResidentialNeutralLandValue`  
- `public System.Single m_CommercialSignificanceConsumers`  
- `public System.Single m_CommercialSignificanceCompetitors`  
- `public System.Single m_CommercialSignificanceWorkplaces`  
- `public System.Single m_CommercialSignificanceLandValue`  
- `public System.Single m_CommercialNeutralLandValue`  
- `public System.Single m_IndustrialSignificanceInput`  
- `public System.Single m_IndustrialSignificanceOutside`  
- `public System.Single m_IndustrialSignificanceLandValue`  
- `public System.Single m_IndustrialNeutralLandValue`  
- `public System.Single m_OfficeSignificanceEmployees`  
- `public System.Single m_OfficeSignificanceServices`  

## Constructors

- `public ZonePreferenceMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

