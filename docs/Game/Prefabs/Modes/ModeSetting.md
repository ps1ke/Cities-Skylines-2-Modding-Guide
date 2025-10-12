# Game.Prefabs.Modes.ModeSetting

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Boolean m_Enable`  
- `public Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector`  
- `public System.Single m_CommercialTaxEffectDemandOffset`  
- `public System.Single m_IndustrialOfficeTaxEffectDemandOffset`  
- `public System.Single m_ResourceDemandPerCitizenMultiplier`  
- `public Unity.Mathematics.float3 m_TaxPaidMultiplier`  
- `public System.Boolean m_SupportPoorCitizens`  
- `public System.Int32 m_MinimumWealth`  
- `public System.Boolean m_EnableGovernmentSubsidies`  
- `public Unity.Mathematics.int2 m_MoneyCoverThreshold`  
- `public System.Int32 m_MaxMoneyCoverPercentage`  
- `public System.Boolean m_EnableAdjustNaturalResources`  
- `public System.Single m_InitialNaturalResourceBoostMultiplier`  
- `public System.Int32 m_PercentOreRefillAmountPerDay`  
- `public System.Int32 m_PercentOilRefillAmountPerDay`  
- `public System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab> m_ModePrefabs`  
- `private System.Collections.Generic.List<Game.Prefabs.Modes.LocalModePrefab> m_LocalModePrefabs`  
- `private System.Collections.Generic.List<Game.Prefabs.Modes.EntityQueryModePrefab> m_GlobalModePrefabs`  

## Constructors

- `public ModeSetting()`  

## Methods

- `public ApplyMode(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  
- `public RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  
- `public StoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

