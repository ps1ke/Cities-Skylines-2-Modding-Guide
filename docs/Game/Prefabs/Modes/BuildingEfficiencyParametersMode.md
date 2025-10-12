# Game.Prefabs.Modes.BuildingEfficiencyParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public UnityEngine.AnimationCurve m_ServiceBudgetEfficiencyFactor`  
- `public System.Single m_LowEfficiencyThreshold`  
- `public System.Single m_ElectricityPenalty`  
- `public System.Int16 m_ElectricityPenaltyDelay`  
- `public UnityEngine.AnimationCurve m_ElectricityFeeFactor`  
- `public System.Single m_WaterPenalty`  
- `public System.Byte m_WaterPenaltyDelay`  
- `public System.Single m_WaterPollutionPenalty`  
- `public System.Single m_SewagePenalty`  
- `public System.Byte m_SewagePenaltyDelay`  
- `public UnityEngine.AnimationCurve m_WaterFeeFactor`  
- `public System.Single m_GarbagePenalty`  
- `public System.Int32 m_NegligibleMail`  
- `public System.Single m_MailEfficiencyPenalty`  
- `public System.Single m_TelecomBaseline`  
- `public System.Single m_MissingEmployeesEfficiencyPenalty`  
- `public System.Int16 m_MissingEmployeesEfficiencyDelay`  
- `public System.Int16 m_ServiceBuildingEfficiencyGracePeriod`  
- `public System.Single m_SickEmployeesEfficiencyPenalty`  

## Constructors

- `public BuildingEfficiencyParametersMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

