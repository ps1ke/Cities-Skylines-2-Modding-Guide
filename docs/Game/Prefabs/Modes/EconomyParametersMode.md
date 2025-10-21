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
public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
```


