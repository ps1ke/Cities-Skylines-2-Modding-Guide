# Game.Prefabs.BuildingEfficiencyParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
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

- `public BuildingEfficiencyParametersPrefab()`  

## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

