# Game.Prefabs.WeatherPhenomenonData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct WeatherPhenomenonData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Single m_OccurenceProbability;
    public System.Single m_HotspotInstability;
    public System.Single m_DamageSeverity;
    public System.Single m_DangerLevel;
    public Colossal.Mathematics.Bounds1 m_PhenomenonRadius;
    public Colossal.Mathematics.Bounds1 m_HotspotRadius;
    public Colossal.Mathematics.Bounds1 m_LightningInterval;
    public Colossal.Mathematics.Bounds1 m_Duration;
    public Colossal.Mathematics.Bounds1 m_OccurenceTemperature;
    public Colossal.Mathematics.Bounds1 m_OccurenceRain;
    public Game.Events.DangerFlags m_DangerFlags;

}
```


## Fields

- `public System.Single m_OccurenceProbability`  

```csharp
public System.Single m_OccurenceProbability;
```

- `public System.Single m_HotspotInstability`  

```csharp
public System.Single m_HotspotInstability;
```

- `public System.Single m_DamageSeverity`  

```csharp
public System.Single m_DamageSeverity;
```

- `public System.Single m_DangerLevel`  

```csharp
public System.Single m_DangerLevel;
```

- `public Colossal.Mathematics.Bounds1 m_PhenomenonRadius`  

```csharp
public Colossal.Mathematics.Bounds1 m_PhenomenonRadius;
```

- `public Colossal.Mathematics.Bounds1 m_HotspotRadius`  

```csharp
public Colossal.Mathematics.Bounds1 m_HotspotRadius;
```

- `public Colossal.Mathematics.Bounds1 m_LightningInterval`  

```csharp
public Colossal.Mathematics.Bounds1 m_LightningInterval;
```

- `public Colossal.Mathematics.Bounds1 m_Duration`  

```csharp
public Colossal.Mathematics.Bounds1 m_Duration;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceTemperature`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceTemperature;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceRain`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceRain;
```

- `public Game.Events.DangerFlags m_DangerFlags`  

```csharp
public Game.Events.DangerFlags m_DangerFlags;
```


