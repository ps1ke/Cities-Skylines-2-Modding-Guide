# Game.Prefabs.Modes.ModeSettingData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ModeSettingData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Boolean m_Enable;
    public Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector;
    public System.Single m_CommercialTaxEffectDemandOffset;
    public System.Single m_IndustrialOfficeTaxEffectDemandOffset;
    public System.Single m_ResourceDemandPerCitizenMultiplier;
    public Unity.Mathematics.float3 m_TaxPaidMultiplier;
    public System.Boolean m_SupportPoorCitizens;
    public System.Int32 m_MinimumWealth;
    public System.Boolean m_EnableGovernmentSubsidies;
    public Unity.Mathematics.int2 m_MoneyCoverThreshold;
    public System.Int32 m_MaxMoneyCoverPercentage;
    public System.Boolean m_EnableAdjustNaturalResources;
    public System.Single m_InitialNaturalResourceBoostMultiplier;
    public System.Int32 m_PercentOreRefillAmountPerDay;
    public System.Int32 m_PercentOilRefillAmountPerDay;

}
```


## Fields

- `public System.Boolean m_Enable`  

```csharp
public System.Boolean m_Enable;
```

- `public Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector`  

```csharp
public Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector;
```

- `public System.Single m_CommercialTaxEffectDemandOffset`  

```csharp
public System.Single m_CommercialTaxEffectDemandOffset;
```

- `public System.Single m_IndustrialOfficeTaxEffectDemandOffset`  

```csharp
public System.Single m_IndustrialOfficeTaxEffectDemandOffset;
```

- `public System.Single m_ResourceDemandPerCitizenMultiplier`  

```csharp
public System.Single m_ResourceDemandPerCitizenMultiplier;
```

- `public Unity.Mathematics.float3 m_TaxPaidMultiplier`  

```csharp
public Unity.Mathematics.float3 m_TaxPaidMultiplier;
```

- `public System.Boolean m_SupportPoorCitizens`  

```csharp
public System.Boolean m_SupportPoorCitizens;
```

- `public System.Int32 m_MinimumWealth`  

```csharp
public System.Int32 m_MinimumWealth;
```

- `public System.Boolean m_EnableGovernmentSubsidies`  

```csharp
public System.Boolean m_EnableGovernmentSubsidies;
```

- `public Unity.Mathematics.int2 m_MoneyCoverThreshold`  

```csharp
public Unity.Mathematics.int2 m_MoneyCoverThreshold;
```

- `public System.Int32 m_MaxMoneyCoverPercentage`  

```csharp
public System.Int32 m_MaxMoneyCoverPercentage;
```

- `public System.Boolean m_EnableAdjustNaturalResources`  

```csharp
public System.Boolean m_EnableAdjustNaturalResources;
```

- `public System.Single m_InitialNaturalResourceBoostMultiplier`  

```csharp
public System.Single m_InitialNaturalResourceBoostMultiplier;
```

- `public System.Int32 m_PercentOreRefillAmountPerDay`  

```csharp
public System.Int32 m_PercentOreRefillAmountPerDay;
```

- `public System.Int32 m_PercentOilRefillAmountPerDay`  

```csharp
public System.Int32 m_PercentOilRefillAmountPerDay;
```


