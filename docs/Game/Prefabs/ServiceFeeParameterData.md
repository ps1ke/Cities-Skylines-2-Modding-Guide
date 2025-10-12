# Game.Prefabs.ServiceFeeParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Fields

- `public Game.Prefabs.FeeParameters m_ElectricityFee`  
- `public Colossal.Collections.AnimationCurve1 m_ElectricityFeeConsumptionMultiplier`  
- `public Game.Prefabs.FeeParameters m_HealthcareFee`  
- `public Game.Prefabs.FeeParameters m_BasicEducationFee`  
- `public Game.Prefabs.FeeParameters m_SecondaryEducationFee`  
- `public Game.Prefabs.FeeParameters m_HigherEducationFee`  
- `public Game.Prefabs.FeeParameters m_GarbageFee`  
- `public Unity.Mathematics.int4 m_GarbageFeeRCIO`  
- `public Game.Prefabs.FeeParameters m_WaterFee`  
- `public Colossal.Collections.AnimationCurve1 m_WaterFeeConsumptionMultiplier`  
- `public Game.Prefabs.FeeParameters m_FireResponseFee`  
- `public Game.Prefabs.FeeParameters m_PoliceFee`  

## Methods

- `public GetDefaultFees() : System.Collections.Generic.IEnumerable<Game.City.ServiceFee>`  
- `private GetDefaultServiceFee(Game.City.PlayerResource resource) : Game.City.ServiceFee`  
- `public GetFeeParameters(Game.City.PlayerResource resource) : Game.Prefabs.FeeParameters`  

## Nested types

- `Game.Prefabs.ServiceFeeParameterData+<GetDefaultFees>d__13`  

