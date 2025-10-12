# Game.Prefabs.Modes.DemandParameterMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Int32 m_MinimumHappiness`  
- `public System.Single m_HappinessEffect`  
- `public Unity.Mathematics.float3 m_TaxEffect`  
- `public System.Single m_StudentEffect`  
- `public System.Single m_AvailableWorkplaceEffect`  
- `public System.Single m_HomelessEffect`  
- `public System.Int32 m_NeutralHappiness`  
- `public System.Single m_NeutralUnemployment`  
- `public System.Single m_NeutralAvailableWorkplacePercentage`  
- `public System.Int32 m_NeutralHomelessness`  
- `public Unity.Mathematics.int3 m_FreeResidentialRequirement`  
- `public System.Single m_CommercialBaseDemand`  
- `public System.Single m_IndustrialBaseDemand`  
- `public System.Single m_ExtractorBaseDemand`  
- `public System.Int32 m_CommuterWorkerRatioLimit`  
- `public System.Int32 m_CommuterSlowSpawnFactor`  
- `public Unity.Mathematics.float4 m_CommuterOCSpawnParameters`  
- `public Unity.Mathematics.float4 m_TouristOCSpawnParameters`  
- `public Unity.Mathematics.float4 m_CitizenOCSpawnParameters`  
- `public System.Single m_TeenSpawnPercentage`  
- `public Unity.Mathematics.int3 m_FrameIntervalForSpawning`  
- `public System.Single m_HouseholdSpawnSpeedFactor`  
- `public System.Single m_HotelRoomPercentRequirement`  
- `public Unity.Mathematics.float4 m_NewCitizenEducationParameters`  

## Constructors

- `public DemandParameterMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

