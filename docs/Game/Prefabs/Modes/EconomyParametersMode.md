# Game.Prefabs.Modes.EconomyParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_ExtractorCompanyExportMultiplier`  
- `public System.Int32 m_Wage0`  
- `public System.Int32 m_Wage1`  
- `public System.Int32 m_Wage2`  
- `public System.Int32 m_Wage3`  
- `public System.Int32 m_Wage4`  
- `public System.Single m_CommuterWageMultiplier`  
- `public System.Single m_CityServiceWageAdjustment`  
- `public System.Int32 m_CompanyBankruptcyLimit`  
- `public System.Int32 m_ResidentialMinimumEarnings`  
- `public System.Int32 m_UnemploymentBenefit`  
- `public System.Int32 m_Pension`  
- `public System.Int32 m_FamilyAllowance`  
- `public Unity.Mathematics.float2 m_ResourceConsumptionMultiplier`  
- `public System.Single m_ResourceConsumptionPerCitizen`  
- `public System.Single m_TouristConsumptionMultiplier`  
- `public System.Single m_WorkDayStart`  
- `public System.Single m_WorkDayEnd`  
- `public System.Single m_IndustrialEfficiency`  
- `public System.Single m_CommercialEfficiency`  
- `public System.Single m_ExtractorProductionEfficiency`  
- `public System.Single m_TrafficReduction`  
- `public System.Single m_MaxCitySpecializationBonus`  
- `public System.Int32 m_ResourceProductionCoefficient`  
- `public System.Single m_MixedBuildingCompanyRentPercentage`  
- `public Unity.Mathematics.float3 m_LandValueModifier`  
- `public Unity.Mathematics.float3 m_RentPriceBuildingZoneTypeBase`  
- `public System.Single m_ResidentialUpkeepLevelExponent`  
- `public System.Single m_CommercialUpkeepLevelExponent`  
- `public System.Single m_IndustrialUpkeepLevelExponent`  
- `public System.Int32 m_PerOfficeResourceNeededForIndustrial`  
- `public System.Single m_UnemploymentAllowanceMaxDays`  
- `public System.Int32 m_ShopPossibilityIncreaseDivider`  
- `public System.Int32 m_PlayerStartMoney`  
- `public Unity.Mathematics.float3 m_BuildRefundPercentage`  
- `public Unity.Mathematics.float3 m_BuildRefundTimeRange`  
- `public System.Single m_RelocationCostMultiplierOverride`  
- `public Unity.Mathematics.float3 m_RoadRefundPercentage`  
- `public Unity.Mathematics.float3 m_RoadRefundTimeRange`  
- `public Unity.Mathematics.int3 m_TreeCostMultipliers`  
- `public UnityEngine.AnimationCurve m_MapTileUpkeepCostMultiplier`  
- `public Unity.Mathematics.float2 m_LoanMinMaxInterestRate`  

## Constructors

- `public EconomyParametersMode()`  

## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  
- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

