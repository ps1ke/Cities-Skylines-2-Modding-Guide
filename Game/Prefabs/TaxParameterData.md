# Game.Prefabs.TaxParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Prefabs.TaxParameterData>`  

## Code

```csharp
public sealed struct TaxParameterData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, System.IEquatable<Game.Prefabs.TaxParameterData>
{
    public Unity.Mathematics.int2 m_TotalTaxLimits;
    public Unity.Mathematics.int2 m_ResidentialTaxLimits;
    public Unity.Mathematics.int2 m_CommercialTaxLimits;
    public Unity.Mathematics.int2 m_IndustrialTaxLimits;
    public Unity.Mathematics.int2 m_OfficeTaxLimits;
    public Unity.Mathematics.int2 m_JobLevelTaxLimits;
    public Unity.Mathematics.int2 m_ResourceTaxLimits;

    public System.Boolean Equals(Game.Prefabs.TaxParameterData other);
}
```


## Fields

- `public Unity.Mathematics.int2 m_TotalTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_TotalTaxLimits;
```

- `public Unity.Mathematics.int2 m_ResidentialTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_ResidentialTaxLimits;
```

- `public Unity.Mathematics.int2 m_CommercialTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_CommercialTaxLimits;
```

- `public Unity.Mathematics.int2 m_IndustrialTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_IndustrialTaxLimits;
```

- `public Unity.Mathematics.int2 m_OfficeTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_OfficeTaxLimits;
```

- `public Unity.Mathematics.int2 m_JobLevelTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_JobLevelTaxLimits;
```

- `public Unity.Mathematics.int2 m_ResourceTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_ResourceTaxLimits;
```


## Methods

- `public Equals(Game.Prefabs.TaxParameterData other) : System.Boolean`  

```csharp
public bool Equals(TaxParameterData other)
	{
		if (m_CommercialTaxLimits.Equals(other.m_CommercialTaxLimits) && m_IndustrialTaxLimits.Equals(other.m_IndustrialTaxLimits) && m_JobLevelTaxLimits.Equals(other.m_JobLevelTaxLimits) && m_OfficeTaxLimits.Equals(other.m_OfficeTaxLimits) && m_ResidentialTaxLimits.Equals(other.m_ResidentialTaxLimits) && m_ResourceTaxLimits.Equals(other.m_ResourceTaxLimits))
		{
			return m_TotalTaxLimits.Equals(other.m_TotalTaxLimits);
		}
		return false;
	}
```


