# Game.Prefabs.ElectricityParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ElectricityParameterData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Single m_InitialBatteryCharge;
    public Colossal.Collections.AnimationCurve1 m_TemperatureConsumptionMultiplier;
    public System.Single m_CloudinessSolarPenalty;
    public Unity.Entities.Entity m_ElectricityServicePrefab;
    public Unity.Entities.Entity m_ElectricityNotificationPrefab;
    public Unity.Entities.Entity m_LowVoltageNotConnectedPrefab;
    public Unity.Entities.Entity m_HighVoltageNotConnectedPrefab;
    public Unity.Entities.Entity m_BottleneckNotificationPrefab;
    public Unity.Entities.Entity m_BuildingBottleneckNotificationPrefab;
    public Unity.Entities.Entity m_NotEnoughProductionNotificationPrefab;
    public Unity.Entities.Entity m_TransformerNotificationPrefab;
    public Unity.Entities.Entity m_NotEnoughConnectedNotificationPrefab;
    public Unity.Entities.Entity m_BatteryEmptyNotificationPrefab;

}
```


## Fields

- `public System.Single m_InitialBatteryCharge`  

```csharp
public System.Single m_InitialBatteryCharge;
```

- `public Colossal.Collections.AnimationCurve1 m_TemperatureConsumptionMultiplier`  

```csharp
public Colossal.Collections.AnimationCurve1 m_TemperatureConsumptionMultiplier;
```

- `public System.Single m_CloudinessSolarPenalty`  

```csharp
public System.Single m_CloudinessSolarPenalty;
```

- `public Unity.Entities.Entity m_ElectricityServicePrefab`  

```csharp
public Unity.Entities.Entity m_ElectricityServicePrefab;
```

- `public Unity.Entities.Entity m_ElectricityNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_ElectricityNotificationPrefab;
```

- `public Unity.Entities.Entity m_LowVoltageNotConnectedPrefab`  

```csharp
public Unity.Entities.Entity m_LowVoltageNotConnectedPrefab;
```

- `public Unity.Entities.Entity m_HighVoltageNotConnectedPrefab`  

```csharp
public Unity.Entities.Entity m_HighVoltageNotConnectedPrefab;
```

- `public Unity.Entities.Entity m_BottleneckNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_BottleneckNotificationPrefab;
```

- `public Unity.Entities.Entity m_BuildingBottleneckNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_BuildingBottleneckNotificationPrefab;
```

- `public Unity.Entities.Entity m_NotEnoughProductionNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_NotEnoughProductionNotificationPrefab;
```

- `public Unity.Entities.Entity m_TransformerNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_TransformerNotificationPrefab;
```

- `public Unity.Entities.Entity m_NotEnoughConnectedNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_NotEnoughConnectedNotificationPrefab;
```

- `public Unity.Entities.Entity m_BatteryEmptyNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_BatteryEmptyNotificationPrefab;
```


