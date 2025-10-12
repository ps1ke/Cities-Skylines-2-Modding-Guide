# Game.Prefabs.Modes.ServiceFeeParameterMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.FeeParameters m_ElectricityFee`  
- `public UnityEngine.AnimationCurve m_ElectricityFeeConsumptionMultiplier`  
- `public Game.Prefabs.FeeParameters m_HealthcareFee`  
- `public Game.Prefabs.FeeParameters m_BasicEducationFee`  
- `public Game.Prefabs.FeeParameters m_SecondaryEducationFee`  
- `public Game.Prefabs.FeeParameters m_HigherEducationFee`  
- `public Game.Prefabs.FeeParameters m_WaterFee`  
- `public UnityEngine.AnimationCurve m_WaterFeeConsumptionMultiplier`  
- `public Game.Prefabs.FeeParameters m_GarbageFee`  
- `public Unity.Mathematics.int4 m_GarbageFeeRCIO`  
- `public Game.Prefabs.FeeParameters m_FireResponseFee`  
- `public Game.Prefabs.FeeParameters m_PoliceFee`  

## Constructors

- `public ServiceFeeParameterMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

