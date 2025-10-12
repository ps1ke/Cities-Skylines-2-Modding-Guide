# Game.Prefabs.Modes.OutsideTradeParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_ElectricityImportPrice`  
- `public System.Single m_ElectricityExportPrice`  
- `public System.Single m_WaterImportPrice`  
- `public System.Single m_WaterExportPrice`  
- `public System.Single m_WaterExportPollutionTolerance`  
- `public System.Single m_SewageExportPrice`  
- `public System.Single m_AirWeightMultiplierOverridden`  
- `public System.Single m_RoadWeightMultiplierOverridden`  
- `public System.Single m_TrainWeightMultiplierOverridden`  
- `public System.Single m_ShipWeightMultiplierOverridden`  
- `public System.Single m_AirDistanceMultiplierOverridden`  
- `public System.Single m_RoadDistanceMultiplierOverridden`  
- `public System.Single m_TrainDistanceMultiplierOverridden`  
- `public System.Single m_ShipDistanceMultiplierOverridden`  
- `public System.Single m_AmbulanceImportServiceFee`  
- `public System.Single m_HearseImportServiceFee`  
- `public System.Single m_FireEngineImportServiceFee`  
- `public System.Single m_GarbageImportServiceFee`  
- `public System.Single m_PoliceImportServiceFee`  
- `public System.Int32 m_OCServiceTradePopulationRange`  

## Constructors

- `public OutsideTradeParametersMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

