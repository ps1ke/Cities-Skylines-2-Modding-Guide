# Game.Prefabs.Modes.CitizenHappinessParameterMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Int32 m_PollutionBonusDivisor`  
- `public System.Int32 m_MaxAirAndGroundPollutionBonus`  
- `public System.Int32 m_MaxNoisePollutionBonus`  
- `public System.Single m_ElectricityWellbeingPenaltyMultiplier`  
- `public System.Byte m_ElectricityPenaltyDelayMultiplier`  
- `public UnityEngine.AnimationCurve m_ElectricityFeeWellbeingEffect`  
- `public System.Int32 m_WaterHealthPenaltyMultiplier`  
- `public System.Int32 m_WaterWellbeingPenaltyMultiplier`  
- `public System.Byte m_WaterPenaltyDelayMultiplier`  
- `public System.Single m_WaterPollutionMultiplierOverriden`  
- `public System.Int32 m_SewageHealthEffectMultiplier`  
- `public System.Int32 m_SewageWellbeingEffectMultiplier`  
- `public System.Byte m_SewagePenaltyDelayMultiplier`  
- `public UnityEngine.AnimationCurve m_WaterFeeHealthEffect`  
- `public UnityEngine.AnimationCurve m_WaterFeeWellbeingEffect`  
- `public System.Int32 m_HealthProblemHealthPenalty`  
- `public System.Int32 m_DeathWellbeingPenalty`  
- `public System.Int32 m_DeathHealthPenalty`  
- `public System.Int32 m_LowWellbeing`  
- `public System.Int32 m_LowHealth`  
- `public System.Int32 m_PenaltyEffect`  
- `public System.Int32 m_HomelessHealthEffect`  
- `public System.Int32 m_HomelessWellbeingEffect`  

## Constructors

- `public CitizenHappinessParameterMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

