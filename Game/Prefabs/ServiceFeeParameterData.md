# Game.Prefabs.ServiceFeeParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ServiceFeeParameterData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.FeeParameters m_ElectricityFee;
    public Colossal.Collections.AnimationCurve1 m_ElectricityFeeConsumptionMultiplier;
    public Game.Prefabs.FeeParameters m_HealthcareFee;
    public Game.Prefabs.FeeParameters m_BasicEducationFee;
    public Game.Prefabs.FeeParameters m_SecondaryEducationFee;
    public Game.Prefabs.FeeParameters m_HigherEducationFee;
    public Game.Prefabs.FeeParameters m_GarbageFee;
    public Unity.Mathematics.int4 m_GarbageFeeRCIO;
    public Game.Prefabs.FeeParameters m_WaterFee;
    public Colossal.Collections.AnimationCurve1 m_WaterFeeConsumptionMultiplier;
    public Game.Prefabs.FeeParameters m_FireResponseFee;
    public Game.Prefabs.FeeParameters m_PoliceFee;

    public System.Collections.Generic.IEnumerable<Game.City.ServiceFee> GetDefaultFees();
    private Game.City.ServiceFee GetDefaultServiceFee(Game.City.PlayerResource resource);
    public Game.Prefabs.FeeParameters GetFeeParameters(Game.City.PlayerResource resource);
}
```


## Fields

- `public Game.Prefabs.FeeParameters m_ElectricityFee`  

```csharp
public Game.Prefabs.FeeParameters m_ElectricityFee;
```

- `public Colossal.Collections.AnimationCurve1 m_ElectricityFeeConsumptionMultiplier`  

```csharp
public Colossal.Collections.AnimationCurve1 m_ElectricityFeeConsumptionMultiplier;
```

- `public Game.Prefabs.FeeParameters m_HealthcareFee`  

```csharp
public Game.Prefabs.FeeParameters m_HealthcareFee;
```

- `public Game.Prefabs.FeeParameters m_BasicEducationFee`  

```csharp
public Game.Prefabs.FeeParameters m_BasicEducationFee;
```

- `public Game.Prefabs.FeeParameters m_SecondaryEducationFee`  

```csharp
public Game.Prefabs.FeeParameters m_SecondaryEducationFee;
```

- `public Game.Prefabs.FeeParameters m_HigherEducationFee`  

```csharp
public Game.Prefabs.FeeParameters m_HigherEducationFee;
```

- `public Game.Prefabs.FeeParameters m_GarbageFee`  

```csharp
public Game.Prefabs.FeeParameters m_GarbageFee;
```

- `public Unity.Mathematics.int4 m_GarbageFeeRCIO`  

```csharp
public Unity.Mathematics.int4 m_GarbageFeeRCIO;
```

- `public Game.Prefabs.FeeParameters m_WaterFee`  

```csharp
public Game.Prefabs.FeeParameters m_WaterFee;
```

- `public Colossal.Collections.AnimationCurve1 m_WaterFeeConsumptionMultiplier`  

```csharp
public Colossal.Collections.AnimationCurve1 m_WaterFeeConsumptionMultiplier;
```

- `public Game.Prefabs.FeeParameters m_FireResponseFee`  

```csharp
public Game.Prefabs.FeeParameters m_FireResponseFee;
```

- `public Game.Prefabs.FeeParameters m_PoliceFee`  

```csharp
public Game.Prefabs.FeeParameters m_PoliceFee;
```


## Methods

- `public GetDefaultFees() : System.Collections.Generic.IEnumerable<Game.City.ServiceFee>`  

```csharp
public IEnumerable<ServiceFee> GetDefaultFees()
	{
		yield return GetDefaultServiceFee(PlayerResource.Healthcare);
		yield return GetDefaultServiceFee(PlayerResource.Electricity);
		yield return GetDefaultServiceFee(PlayerResource.BasicEducation);
		yield return GetDefaultServiceFee(PlayerResource.HigherEducation);
		yield return GetDefaultServiceFee(PlayerResource.SecondaryEducation);
		yield return GetDefaultServiceFee(PlayerResource.Garbage);
		yield return GetDefaultServiceFee(PlayerResource.Water);
		yield return GetDefaultServiceFee(PlayerResource.FireResponse);
		yield return GetDefaultServiceFee(PlayerResource.Police);
	}
```

- `private GetDefaultServiceFee(Game.City.PlayerResource resource) : Game.City.ServiceFee`  

```csharp
private ServiceFee GetDefaultServiceFee(PlayerResource resource)
	{
		return new ServiceFee
		{
			m_Resource = resource,
			m_Fee = GetFeeParameters(resource).m_Default
		};
	}
```

- `public GetFeeParameters(Game.City.PlayerResource resource) : Game.Prefabs.FeeParameters`  

```csharp
public FeeParameters GetFeeParameters(PlayerResource resource)
	{
		return resource switch
		{
			PlayerResource.Healthcare => m_HealthcareFee, 
			PlayerResource.Electricity => m_ElectricityFee, 
			PlayerResource.BasicEducation => m_BasicEducationFee, 
			PlayerResource.HigherEducation => m_HigherEducationFee, 
			PlayerResource.SecondaryEducation => m_SecondaryEducationFee, 
			PlayerResource.Garbage => m_GarbageFee, 
			PlayerResource.Water => m_WaterFee, 
			PlayerResource.FireResponse => m_FireResponseFee, 
			PlayerResource.Police => m_PoliceFee, 
			_ => default(FeeParameters), 
		};
	}
```


## Nested types

- `Game.Prefabs.ServiceFeeParameterData+<GetDefaultFees>d__13`  

