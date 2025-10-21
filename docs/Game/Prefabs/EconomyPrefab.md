# Game.Prefabs.EconomyPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EconomyPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
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
    public System.Single m_ExtractorEfficiency;
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
    public System.Single m_RelocationCostMultiplier;
    public Unity.Mathematics.float3 m_RoadRefundPercentage;
    public Unity.Mathematics.float3 m_RoadRefundTimeRange;
    public Unity.Mathematics.int3 m_TreeCostMultipliers;
    public UnityEngine.AnimationCurve m_MapTileUpkeepCostMultiplier;
    public Unity.Mathematics.float2 m_LoanMinMaxInterestRate;

    public EconomyPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
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

- `public System.Single m_ExtractorEfficiency`  

```csharp
public System.Single m_ExtractorEfficiency;
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

- `public System.Single m_RelocationCostMultiplier`  

```csharp
public System.Single m_RelocationCostMultiplier;
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

- `public EconomyPrefab()`  

```csharp
public EconomyPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


