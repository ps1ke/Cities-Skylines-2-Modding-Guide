# Game.Prefabs.Modes.EconomyParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EconomyParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ExtractorCompanyExportMultiplier;
    public System.Int32 m_Wage0;
    public System.Int32 m_Wage1;
    public System.Int32 m_Wage2;
    public System.Int32 m_Wage3;
    public System.Int32 m_Wage4;
    public System.Single m_CommuterWageMultiplier;
    public System.Single m_CityServiceWageAdjustment;
    public System.Int32 m_CompanyBankruptcyLimit;
    public System.Int32 m_ResidentialMinimumEarnings;
    public System.Int32 m_UnemploymentBenefit;
    public System.Int32 m_Pension;
    public System.Int32 m_FamilyAllowance;
    public Unity.Mathematics.float2 m_ResourceConsumptionMultiplier;
    public System.Single m_ResourceConsumptionPerCitizen;
    public System.Single m_TouristConsumptionMultiplier;
    public System.Single m_WorkDayStart;
    public System.Single m_WorkDayEnd;
    public System.Single m_IndustrialEfficiency;
    public System.Single m_CommercialEfficiency;
    public System.Single m_ExtractorProductionEfficiency;
    public System.Single m_TrafficReduction;
    public System.Single m_MaxCitySpecializationBonus;
    public System.Int32 m_ResourceProductionCoefficient;
    public System.Single m_MixedBuildingCompanyRentPercentage;
    public Unity.Mathematics.float3 m_LandValueModifier;
    public Unity.Mathematics.float3 m_RentPriceBuildingZoneTypeBase;
    public System.Single m_ResidentialUpkeepLevelExponent;
    public System.Single m_CommercialUpkeepLevelExponent;
    public System.Single m_IndustrialUpkeepLevelExponent;
    public System.Int32 m_PerOfficeResourceNeededForIndustrial;
    public System.Single m_UnemploymentAllowanceMaxDays;
    public System.Int32 m_ShopPossibilityIncreaseDivider;
    public System.Int32 m_PlayerStartMoney;
    public Unity.Mathematics.float3 m_BuildRefundPercentage;
    public Unity.Mathematics.float3 m_BuildRefundTimeRange;
    public System.Single m_RelocationCostMultiplierOverride;
    public Unity.Mathematics.float3 m_RoadRefundPercentage;
    public Unity.Mathematics.float3 m_RoadRefundTimeRange;
    public Unity.Mathematics.int3 m_TreeCostMultipliers;
    public UnityEngine.AnimationCurve m_MapTileUpkeepCostMultiplier;
    public Unity.Mathematics.float2 m_LoanMinMaxInterestRate;

    public EconomyParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_ExtractorCompanyExportMultiplier`  

```csharp
public System.Single m_ExtractorCompanyExportMultiplier;
```

- `public System.Int32 m_Wage0`  

```csharp
public System.Int32 m_Wage0;
```

- `public System.Int32 m_Wage1`  

```csharp
public System.Int32 m_Wage1;
```

- `public System.Int32 m_Wage2`  

```csharp
public System.Int32 m_Wage2;
```

- `public System.Int32 m_Wage3`  

```csharp
public System.Int32 m_Wage3;
```

- `public System.Int32 m_Wage4`  

```csharp
public System.Int32 m_Wage4;
```

- `public System.Single m_CommuterWageMultiplier`  

```csharp
public System.Single m_CommuterWageMultiplier;
```

- `public System.Single m_CityServiceWageAdjustment`  

```csharp
public System.Single m_CityServiceWageAdjustment;
```

- `public System.Int32 m_CompanyBankruptcyLimit`  

```csharp
public System.Int32 m_CompanyBankruptcyLimit;
```

- `public System.Int32 m_ResidentialMinimumEarnings`  

```csharp
public System.Int32 m_ResidentialMinimumEarnings;
```

- `public System.Int32 m_UnemploymentBenefit`  

```csharp
public System.Int32 m_UnemploymentBenefit;
```

- `public System.Int32 m_Pension`  

```csharp
public System.Int32 m_Pension;
```

- `public System.Int32 m_FamilyAllowance`  

```csharp
public System.Int32 m_FamilyAllowance;
```

- `public Unity.Mathematics.float2 m_ResourceConsumptionMultiplier`  

```csharp
public Unity.Mathematics.float2 m_ResourceConsumptionMultiplier;
```

- `public System.Single m_ResourceConsumptionPerCitizen`  

```csharp
public System.Single m_ResourceConsumptionPerCitizen;
```

- `public System.Single m_TouristConsumptionMultiplier`  

```csharp
public System.Single m_TouristConsumptionMultiplier;
```

- `public System.Single m_WorkDayStart`  

```csharp
public System.Single m_WorkDayStart;
```

- `public System.Single m_WorkDayEnd`  

```csharp
public System.Single m_WorkDayEnd;
```

- `public System.Single m_IndustrialEfficiency`  

```csharp
public System.Single m_IndustrialEfficiency;
```

- `public System.Single m_CommercialEfficiency`  

```csharp
public System.Single m_CommercialEfficiency;
```

- `public System.Single m_ExtractorProductionEfficiency`  

```csharp
public System.Single m_ExtractorProductionEfficiency;
```

- `public System.Single m_TrafficReduction`  

```csharp
public System.Single m_TrafficReduction;
```

- `public System.Single m_MaxCitySpecializationBonus`  

```csharp
public System.Single m_MaxCitySpecializationBonus;
```

- `public System.Int32 m_ResourceProductionCoefficient`  

```csharp
public System.Int32 m_ResourceProductionCoefficient;
```

- `public System.Single m_MixedBuildingCompanyRentPercentage`  

```csharp
public System.Single m_MixedBuildingCompanyRentPercentage;
```

- `public Unity.Mathematics.float3 m_LandValueModifier`  

```csharp
public Unity.Mathematics.float3 m_LandValueModifier;
```

- `public Unity.Mathematics.float3 m_RentPriceBuildingZoneTypeBase`  

```csharp
public Unity.Mathematics.float3 m_RentPriceBuildingZoneTypeBase;
```

- `public System.Single m_ResidentialUpkeepLevelExponent`  

```csharp
public System.Single m_ResidentialUpkeepLevelExponent;
```

- `public System.Single m_CommercialUpkeepLevelExponent`  

```csharp
public System.Single m_CommercialUpkeepLevelExponent;
```

- `public System.Single m_IndustrialUpkeepLevelExponent`  

```csharp
public System.Single m_IndustrialUpkeepLevelExponent;
```

- `public System.Int32 m_PerOfficeResourceNeededForIndustrial`  

```csharp
public System.Int32 m_PerOfficeResourceNeededForIndustrial;
```

- `public System.Single m_UnemploymentAllowanceMaxDays`  

```csharp
public System.Single m_UnemploymentAllowanceMaxDays;
```

- `public System.Int32 m_ShopPossibilityIncreaseDivider`  

```csharp
public System.Int32 m_ShopPossibilityIncreaseDivider;
```

- `public System.Int32 m_PlayerStartMoney`  

```csharp
public System.Int32 m_PlayerStartMoney;
```

- `public Unity.Mathematics.float3 m_BuildRefundPercentage`  

```csharp
public Unity.Mathematics.float3 m_BuildRefundPercentage;
```

- `public Unity.Mathematics.float3 m_BuildRefundTimeRange`  

```csharp
public Unity.Mathematics.float3 m_BuildRefundTimeRange;
```

- `public System.Single m_RelocationCostMultiplierOverride`  

```csharp
public System.Single m_RelocationCostMultiplierOverride;
```

- `public Unity.Mathematics.float3 m_RoadRefundPercentage`  

```csharp
public Unity.Mathematics.float3 m_RoadRefundPercentage;
```

- `public Unity.Mathematics.float3 m_RoadRefundTimeRange`  

```csharp
public Unity.Mathematics.float3 m_RoadRefundTimeRange;
```

- `public Unity.Mathematics.int3 m_TreeCostMultipliers`  

```csharp
public Unity.Mathematics.int3 m_TreeCostMultipliers;
```

- `public UnityEngine.AnimationCurve m_MapTileUpkeepCostMultiplier`  

```csharp
public UnityEngine.AnimationCurve m_MapTileUpkeepCostMultiplier;
```

- `public Unity.Mathematics.float2 m_LoanMinMaxInterestRate`  

```csharp
public Unity.Mathematics.float2 m_LoanMinMaxInterestRate;
```


## Constructors

- `public EconomyParametersMode()`  

```csharp
public EconomyParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		EconomyParameterData componentData = entityManager.GetComponentData<EconomyParameterData>(singletonEntity);
		componentData.m_ExtractorCompanyExportMultiplier = m_ExtractorCompanyExportMultiplier;
		componentData.m_Wage0 = m_Wage0;
		componentData.m_Wage1 = m_Wage1;
		componentData.m_Wage2 = m_Wage2;
		componentData.m_Wage3 = m_Wage3;
		componentData.m_Wage4 = m_Wage4;
		componentData.m_CommuterWageMultiplier = m_CommuterWageMultiplier;
		componentData.m_CityServiceWageAdjustment = m_CityServiceWageAdjustment;
		componentData.m_CompanyBankruptcyLimit = m_CompanyBankruptcyLimit;
		componentData.m_ResidentialMinimumEarnings = m_ResidentialMinimumEarnings;
		componentData.m_UnemploymentBenefit = m_UnemploymentBenefit;
		componentData.m_Pension = m_Pension;
		componentData.m_FamilyAllowance = m_FamilyAllowance;
		componentData.m_ResourceConsumptionMultiplier = m_ResourceConsumptionMultiplier;
		componentData.m_ResourceConsumptionPerCitizen = m_ResourceConsumptionPerCitizen;
		componentData.m_TouristConsumptionMultiplier = m_TouristConsumptionMultiplier;
		componentData.m_WorkDayStart = m_WorkDayStart;
		componentData.m_WorkDayEnd = m_WorkDayEnd;
		componentData.m_IndustrialEfficiency = m_IndustrialEfficiency;
		componentData.m_CommercialEfficiency = m_CommercialEfficiency;
		componentData.m_ExtractorProductionEfficiency = m_ExtractorProductionEfficiency;
		componentData.m_TrafficReduction = m_TrafficReduction;
		componentData.m_MaxCitySpecializationBonus = m_MaxCitySpecializationBonus;
		componentData.m_ResourceProductionCoefficient = m_ResourceProductionCoefficient;
		componentData.m_MixedBuildingCompanyRentPercentage = m_MixedBuildingCompanyRentPercentage;
		componentData.m_LandValueModifier = m_LandValueModifier;
		componentData.m_RentPriceBuildingZoneTypeBase = m_RentPriceBuildingZoneTypeBase;
		componentData.m_ResidentialUpkeepLevelExponent = m_ResidentialUpkeepLevelExponent;
		componentData.m_CommercialUpkeepLevelExponent = m_CommercialUpkeepLevelExponent;
		componentData.m_IndustrialUpkeepLevelExponent = m_IndustrialUpkeepLevelExponent;
		componentData.m_PerOfficeResourceNeededForIndustrial = m_PerOfficeResourceNeededForIndustrial;
		componentData.m_UnemploymentAllowanceMaxDays = m_UnemploymentAllowanceMaxDays;
		componentData.m_ShopPossibilityIncreaseDivider = m_ShopPossibilityIncreaseDivider;
		componentData.m_PlayerStartMoney = m_PlayerStartMoney;
		componentData.m_BuildRefundPercentage = m_BuildRefundPercentage;
		componentData.m_BuildRefundTimeRange = m_BuildRefundTimeRange;
		componentData.m_RelocationCostMultiplier = m_RelocationCostMultiplierOverride;
		componentData.m_RoadRefundPercentage = m_RoadRefundPercentage;
		componentData.m_RoadRefundTimeRange = m_RoadRefundTimeRange;
		componentData.m_TreeCostMultipliers = m_TreeCostMultipliers;
		componentData.m_MapTileUpkeepCostMultiplier = new AnimationCurve1(m_MapTileUpkeepCostMultiplier);
		componentData.m_LoanMinMaxInterestRate = m_LoanMinMaxInterestRate;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<EconomyParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<EconomyParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		EconomyPrefab economyPrefab = prefabSystem.GetPrefab<EconomyPrefab>(entity);
		EconomyParameterData componentData = entityManager.GetComponentData<EconomyParameterData>(entity);
		componentData.m_ExtractorCompanyExportMultiplier = economyPrefab.m_ExtractorCompanyExportMultiplier;
		componentData.m_Wage0 = economyPrefab.m_Wage0;
		componentData.m_Wage1 = economyPrefab.m_Wage1;
		componentData.m_Wage2 = economyPrefab.m_Wage2;
		componentData.m_Wage3 = economyPrefab.m_Wage3;
		componentData.m_Wage4 = economyPrefab.m_Wage4;
		componentData.m_CommuterWageMultiplier = economyPrefab.m_CommuterWageMultiplier;
		componentData.m_CityServiceWageAdjustment = economyPrefab.m_CityServiceWageAdjustment;
		componentData.m_CompanyBankruptcyLimit = economyPrefab.m_CompanyBankruptcyLimit;
		componentData.m_ResidentialMinimumEarnings = economyPrefab.m_ResidentialMinimumEarnings;
		componentData.m_UnemploymentBenefit = economyPrefab.m_UnemploymentBenefit;
		componentData.m_Pension = economyPrefab.m_Pension;
		componentData.m_FamilyAllowance = economyPrefab.m_FamilyAllowance;
		componentData.m_ResourceConsumptionMultiplier = economyPrefab.m_ResourceConsumptionMultiplier;
		componentData.m_ResourceConsumptionPerCitizen = economyPrefab.m_ResourceConsumptionPerCitizen;
		componentData.m_TouristConsumptionMultiplier = economyPrefab.m_TouristConsumptionMultiplier;
		componentData.m_WorkDayStart = economyPrefab.m_WorkDayStart;
		componentData.m_WorkDayEnd = economyPrefab.m_WorkDayEnd;
		componentData.m_IndustrialEfficiency = economyPrefab.m_IndustrialEfficiency;
		componentData.m_CommercialEfficiency = economyPrefab.m_CommercialEfficiency;
		componentData.m_ExtractorProductionEfficiency = economyPrefab.m_ExtractorEfficiency;
		componentData.m_TrafficReduction = economyPrefab.m_TrafficReduction;
		componentData.m_MaxCitySpecializationBonus = economyPrefab.m_MaxCitySpecializationBonus;
		componentData.m_ResourceProductionCoefficient = economyPrefab.m_ResourceProductionCoefficient;
		componentData.m_MixedBuildingCompanyRentPercentage = economyPrefab.m_MixedBuildingCompanyRentPercentage;
		componentData.m_LandValueModifier = economyPrefab.m_LandValueModifier;
		componentData.m_RentPriceBuildingZoneTypeBase = economyPrefab.m_RentPriceBuildingZoneTypeBase;
		componentData.m_ResidentialUpkeepLevelExponent = economyPrefab.m_ResidentialUpkeepLevelExponent;
		componentData.m_CommercialUpkeepLevelExponent = economyPrefab.m_CommercialUpkeepLevelExponent;
		componentData.m_IndustrialUpkeepLevelExponent = economyPrefab.m_IndustrialUpkeepLevelExponent;
		componentData.m_PerOfficeResourceNeededForIndustrial = economyPrefab.m_PerOfficeResourceNeededForIndustrial;
		componentData.m_UnemploymentAllowanceMaxDays = economyPrefab.m_UnemploymentAllowanceMaxDays;
		componentData.m_ShopPossibilityIncreaseDivider = economyPrefab.m_ShopPossibilityIncreaseDivider;
		componentData.m_PlayerStartMoney = economyPrefab.m_PlayerStartMoney;
		componentData.m_BuildRefundPercentage = economyPrefab.m_BuildRefundPercentage;
		componentData.m_BuildRefundTimeRange = economyPrefab.m_BuildRefundTimeRange;
		componentData.m_RelocationCostMultiplier = economyPrefab.m_RelocationCostMultiplier;
		componentData.m_RoadRefundPercentage = economyPrefab.m_RoadRefundPercentage;
		componentData.m_RoadRefundTimeRange = economyPrefab.m_RoadRefundTimeRange;
		componentData.m_TreeCostMultipliers = economyPrefab.m_TreeCostMultipliers;
		componentData.m_MapTileUpkeepCostMultiplier = new AnimationCurve1(economyPrefab.m_MapTileUpkeepCostMultiplier);
		componentData.m_LoanMinMaxInterestRate = economyPrefab.m_LoanMinMaxInterestRate;
		entityManager.SetComponentData(entity, componentData);
	}
```


