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
public System.Collections.Generic.IEnumerable<Game.City.ServiceFee> GetDefaultFees();
```

- `private GetDefaultServiceFee(Game.City.PlayerResource resource) : Game.City.ServiceFee`  

```csharp
private Game.City.ServiceFee GetDefaultServiceFee(Game.City.PlayerResource resource);
```

- `public GetFeeParameters(Game.City.PlayerResource resource) : Game.Prefabs.FeeParameters`  

```csharp
public Game.Prefabs.FeeParameters GetFeeParameters(Game.City.PlayerResource resource);
```


## Nested types

- `Game.Prefabs.ServiceFeeParameterData+<GetDefaultFees>d__13`  

