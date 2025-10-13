# Game.Prefabs.WaterPipeParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct WaterPipeParameterData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_WaterService;
    public Unity.Entities.Entity m_WaterNotification;
    public Unity.Entities.Entity m_DirtyWaterNotification;
    public Unity.Entities.Entity m_SewageNotification;
    public Unity.Entities.Entity m_WaterPipeNotConnectedNotification;
    public Unity.Entities.Entity m_SewagePipeNotConnectedNotification;
    public Unity.Entities.Entity m_NotEnoughWaterCapacityNotification;
    public Unity.Entities.Entity m_NotEnoughSewageCapacityNotification;
    public Unity.Entities.Entity m_NotEnoughGroundwaterNotification;
    public Unity.Entities.Entity m_NotEnoughSurfaceWaterNotification;
    public Unity.Entities.Entity m_DirtyWaterPumpNotification;
    public System.Single m_GroundwaterReplenish;
    public System.Int32 m_GroundwaterPurification;
    public System.Single m_GroundwaterUsageMultiplier;
    public System.Single m_GroundwaterPumpEffectiveAmount;
    public System.Single m_SurfaceWaterUsageMultiplier;
    public System.Single m_SurfaceWaterPumpEffectiveDepth;
    public System.Single m_MaxToleratedPollution;
    public System.Int32 m_WaterPipePollutionSpreadInterval;
    public System.Single m_StaleWaterPipePurification;

}
```


## Fields

- `public Unity.Entities.Entity m_WaterService`  

```csharp
public Unity.Entities.Entity m_WaterService;
```

- `public Unity.Entities.Entity m_WaterNotification`  

```csharp
public Unity.Entities.Entity m_WaterNotification;
```

- `public Unity.Entities.Entity m_DirtyWaterNotification`  

```csharp
public Unity.Entities.Entity m_DirtyWaterNotification;
```

- `public Unity.Entities.Entity m_SewageNotification`  

```csharp
public Unity.Entities.Entity m_SewageNotification;
```

- `public Unity.Entities.Entity m_WaterPipeNotConnectedNotification`  

```csharp
public Unity.Entities.Entity m_WaterPipeNotConnectedNotification;
```

- `public Unity.Entities.Entity m_SewagePipeNotConnectedNotification`  

```csharp
public Unity.Entities.Entity m_SewagePipeNotConnectedNotification;
```

- `public Unity.Entities.Entity m_NotEnoughWaterCapacityNotification`  

```csharp
public Unity.Entities.Entity m_NotEnoughWaterCapacityNotification;
```

- `public Unity.Entities.Entity m_NotEnoughSewageCapacityNotification`  

```csharp
public Unity.Entities.Entity m_NotEnoughSewageCapacityNotification;
```

- `public Unity.Entities.Entity m_NotEnoughGroundwaterNotification`  

```csharp
public Unity.Entities.Entity m_NotEnoughGroundwaterNotification;
```

- `public Unity.Entities.Entity m_NotEnoughSurfaceWaterNotification`  

```csharp
public Unity.Entities.Entity m_NotEnoughSurfaceWaterNotification;
```

- `public Unity.Entities.Entity m_DirtyWaterPumpNotification`  

```csharp
public Unity.Entities.Entity m_DirtyWaterPumpNotification;
```

- `public System.Single m_GroundwaterReplenish`  

```csharp
public System.Single m_GroundwaterReplenish;
```

- `public System.Int32 m_GroundwaterPurification`  

```csharp
public System.Int32 m_GroundwaterPurification;
```

- `public System.Single m_GroundwaterUsageMultiplier`  

```csharp
public System.Single m_GroundwaterUsageMultiplier;
```

- `public System.Single m_GroundwaterPumpEffectiveAmount`  

```csharp
public System.Single m_GroundwaterPumpEffectiveAmount;
```

- `public System.Single m_SurfaceWaterUsageMultiplier`  

```csharp
public System.Single m_SurfaceWaterUsageMultiplier;
```

- `public System.Single m_SurfaceWaterPumpEffectiveDepth`  

```csharp
public System.Single m_SurfaceWaterPumpEffectiveDepth;
```

- `public System.Single m_MaxToleratedPollution`  

```csharp
public System.Single m_MaxToleratedPollution;
```

- `public System.Int32 m_WaterPipePollutionSpreadInterval`  

```csharp
public System.Int32 m_WaterPipePollutionSpreadInterval;
```

- `public System.Single m_StaleWaterPipePurification`  

```csharp
public System.Single m_StaleWaterPipePurification;
```


