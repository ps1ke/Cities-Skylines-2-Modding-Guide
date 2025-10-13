# Game.Prefabs.WeatherAudioData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct WeatherAudioData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Single m_StartRaininess;
    public System.Single m_RainAudioIntensity;
    public System.Single m_RainFadeInSpeed;
    public System.Single m_RainFadeOutSpeed;
    public System.Single m_RainVolumeDeclineExponent;
    public System.Single m_RainVolumeMaxZoomPercentage;
    public System.Single m_LightningSoundSpeed;
    public Unity.Mathematics.float2 m_MinMaxRaininessPitch;
    public Unity.Entities.Entity m_RainAudio;
    public System.Single m_WaterAudioIntensity;
    public System.Single m_WaterFadeSpeed;
    public System.Int32 m_WaterAudioEnabledZoom;
    public System.Int32 m_WaterAudioNearDistance;
    public Unity.Entities.Entity m_WaterAmbientAudio;
    public Unity.Entities.Entity m_LightningAudio;

}
```


## Fields

- `public System.Single m_StartRaininess`  

```csharp
public System.Single m_StartRaininess;
```

- `public System.Single m_RainAudioIntensity`  

```csharp
public System.Single m_RainAudioIntensity;
```

- `public System.Single m_RainFadeInSpeed`  

```csharp
public System.Single m_RainFadeInSpeed;
```

- `public System.Single m_RainFadeOutSpeed`  

```csharp
public System.Single m_RainFadeOutSpeed;
```

- `public System.Single m_RainVolumeDeclineExponent`  

```csharp
public System.Single m_RainVolumeDeclineExponent;
```

- `public System.Single m_RainVolumeMaxZoomPercentage`  

```csharp
public System.Single m_RainVolumeMaxZoomPercentage;
```

- `public System.Single m_LightningSoundSpeed`  

```csharp
public System.Single m_LightningSoundSpeed;
```

- `public Unity.Mathematics.float2 m_MinMaxRaininessPitch`  

```csharp
public Unity.Mathematics.float2 m_MinMaxRaininessPitch;
```

- `public Unity.Entities.Entity m_RainAudio`  

```csharp
public Unity.Entities.Entity m_RainAudio;
```

- `public System.Single m_WaterAudioIntensity`  

```csharp
public System.Single m_WaterAudioIntensity;
```

- `public System.Single m_WaterFadeSpeed`  

```csharp
public System.Single m_WaterFadeSpeed;
```

- `public System.Int32 m_WaterAudioEnabledZoom`  

```csharp
public System.Int32 m_WaterAudioEnabledZoom;
```

- `public System.Int32 m_WaterAudioNearDistance`  

```csharp
public System.Int32 m_WaterAudioNearDistance;
```

- `public Unity.Entities.Entity m_WaterAmbientAudio`  

```csharp
public Unity.Entities.Entity m_WaterAmbientAudio;
```

- `public Unity.Entities.Entity m_LightningAudio`  

```csharp
public Unity.Entities.Entity m_LightningAudio;
```


