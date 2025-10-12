# Game.Prefabs.Modes.PoliceConfigurationMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_MaxCrimeAccumulationMultiplier`  
- `public System.Single m_CrimeAccumulationToleranceMultiplier`  
- `public System.Int32 m_HomeCrimeEffectMultiplier`  
- `public System.Int32 m_WorkplaceCrimeEffectMultiplier`  
- `public System.Single m_WelfareCrimeRecurrenceFactor`  
- `public System.Single m_CrimePoliceCoverageFactorMultiflier`  
- `public System.Single m_CrimePopulationReductionMultiplier`  

## Constructors

- `public PoliceConfigurationMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

