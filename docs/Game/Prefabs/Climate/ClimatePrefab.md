# Game.Prefabs.Climate.ClimatePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ClimatePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Colossal.UI.Binding.IJsonWritable
{
    public System.Single m_Latitude;
    public System.Single m_Longitude;
    public System.Single m_FreezingTemperature;
    public UnityEngine.AnimationCurve m_Temperature;
    public UnityEngine.AnimationCurve m_Precipitation;
    public UnityEngine.AnimationCurve m_Cloudiness;
    public UnityEngine.AnimationCurve m_Aurora;
    public UnityEngine.AnimationCurve m_Fog;
    public Game.Prefabs.Climate.WeatherPrefab m_DefaultWeather;
    public Game.Prefabs.Climate.WeatherPrefab[] m_DefaultWeathers;
    public Game.Simulation.ClimateSystem+SeasonInfo[] m_Seasons;
    public System.Int32 m_RandomSeed;
    private System.Int32[] m_SeasonsOrder;
    public static const System.Int32 kYearDuration;
    private static const System.Single k90PercentileToStdDev;

    public Colossal.Mathematics.Bounds1 temperatureRange { get; }
    public System.Single averageCloudiness { get; }
    public System.Single averagePrecipitation { get; }

    public ClimatePrefab();

    private System.Single <EnsureSeasonsOrder>b__16_0(System.Int32 v);
    public System.Int32 CountElapsedSeasons(System.Single startTime, System.Single elapsedTime);
    public Game.Prefabs.Climate.ClimatePrefab+SeasonAuroraCurves CreateSeasonAuroraCurves();
    public Game.Prefabs.Climate.ClimatePrefab+SeasonPrecipCurves CreateSeasonPrecipCurves();
    public Game.Prefabs.Climate.ClimatePrefab+SeasonTempCurves CreateSeasonTemperatureCurves();
    internal System.Void EnsureSeasonsOrder(System.Boolean force);
    public System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single, System.Single> FindSeasonByTime(System.Single time);
    private static System.Single GaussianRandom(System.Single mean, System.Single dev, Unity.Mathematics.Random& rng);
    private static UnityEngine.AnimationCurve GenCurveFromMinMax(System.Int32 keyCount, UnityEngine.AnimationCurve cmin, UnityEngine.AnimationCurve cmax, System.UInt32 seed, System.Single minValue, System.Single maxValue);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single> GetSeasonAndMidTime(System.Int32 index);
    private System.Single GetSeasonMidTime(System.Int32 index);
    private System.Boolean Intersect(System.Single startTime, System.Single elapsedTime, System.Single seasonStart, System.Single seasonEnd);
    private static System.Void LoopCurve(UnityEngine.AnimationCurve curve, System.Single minValue, System.Single maxValue);
    private System.Void RebuildAuroraCurves(System.UInt32 seed);
    public System.Void RebuildCurves();
    private System.Void RebuildFogCurves(System.UInt32 seed);
    private System.Void RebuildPrecipitationCurves(System.UInt32 seed);
    private System.Void RebuildTemperatureCurves(System.UInt32 seed);
    private static System.Single SmoothNoise(System.Single x, System.Single y);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Single m_Latitude`  

```csharp
public System.Single m_Latitude;
```

- `public System.Single m_Longitude`  

```csharp
public System.Single m_Longitude;
```

- `public System.Single m_FreezingTemperature`  

```csharp
public System.Single m_FreezingTemperature;
```

- `public UnityEngine.AnimationCurve m_Temperature`  

```csharp
public UnityEngine.AnimationCurve m_Temperature;
```

- `public UnityEngine.AnimationCurve m_Precipitation`  

```csharp
public UnityEngine.AnimationCurve m_Precipitation;
```

- `public UnityEngine.AnimationCurve m_Cloudiness`  

```csharp
public UnityEngine.AnimationCurve m_Cloudiness;
```

- `public UnityEngine.AnimationCurve m_Aurora`  

```csharp
public UnityEngine.AnimationCurve m_Aurora;
```

- `public UnityEngine.AnimationCurve m_Fog`  

```csharp
public UnityEngine.AnimationCurve m_Fog;
```

- `public Game.Prefabs.Climate.WeatherPrefab m_DefaultWeather`  

```csharp
public Game.Prefabs.Climate.WeatherPrefab m_DefaultWeather;
```

- `public Game.Prefabs.Climate.WeatherPrefab[] m_DefaultWeathers`  

```csharp
public Game.Prefabs.Climate.WeatherPrefab[] m_DefaultWeathers;
```

- `public Game.Simulation.ClimateSystem+SeasonInfo[] m_Seasons`  

```csharp
public Game.Simulation.ClimateSystem+SeasonInfo[] m_Seasons;
```

- `public System.Int32 m_RandomSeed`  

```csharp
public System.Int32 m_RandomSeed;
```

- `private System.Int32[] m_SeasonsOrder`  

```csharp
private System.Int32[] m_SeasonsOrder;
```

- `public static const System.Int32 kYearDuration`  

```csharp
public static const System.Int32 kYearDuration;
```

- `private static const System.Single k90PercentileToStdDev`  

```csharp
private static const System.Single k90PercentileToStdDev;
```


## Properties

- `public Colossal.Mathematics.Bounds1 temperatureRange { get }`  

```csharp
public Colossal.Mathematics.Bounds1 temperatureRange { get; }
```

- `public System.Single averageCloudiness { get }`  

```csharp
public System.Single averageCloudiness { get; }
```

- `public System.Single averagePrecipitation { get }`  

```csharp
public System.Single averagePrecipitation { get; }
```


## Constructors

- `public ClimatePrefab()`  

```csharp
public ClimatePrefab();
```


## Methods

- `private <EnsureSeasonsOrder>b__16_0(System.Int32 v) : System.Single`  

```csharp
private System.Single <EnsureSeasonsOrder>b__16_0(System.Int32 v);
```

- `public CountElapsedSeasons(System.Single startTime, System.Single elapsedTime) : System.Int32`  

```csharp
public System.Int32 CountElapsedSeasons(System.Single startTime, System.Single elapsedTime);
```

- `public CreateSeasonAuroraCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonAuroraCurves`  

```csharp
public Game.Prefabs.Climate.ClimatePrefab+SeasonAuroraCurves CreateSeasonAuroraCurves();
```

- `public CreateSeasonPrecipCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonPrecipCurves`  

```csharp
public Game.Prefabs.Climate.ClimatePrefab+SeasonPrecipCurves CreateSeasonPrecipCurves();
```

- `public CreateSeasonTemperatureCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonTempCurves`  

```csharp
public Game.Prefabs.Climate.ClimatePrefab+SeasonTempCurves CreateSeasonTemperatureCurves();
```

- `internal EnsureSeasonsOrder(System.Boolean force = False) : System.Void`  

```csharp
internal System.Void EnsureSeasonsOrder(System.Boolean force);
```

- `public FindSeasonByTime(System.Single time) : System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single, System.Single>`  

```csharp
public System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single, System.Single> FindSeasonByTime(System.Single time);
```

- `private static GaussianRandom(System.Single mean, System.Single dev, Unity.Mathematics.Random& rng) : System.Single`  

```csharp
private static System.Single GaussianRandom(System.Single mean, System.Single dev, Unity.Mathematics.Random& rng);
```

- `private static GenCurveFromMinMax(System.Int32 keyCount, UnityEngine.AnimationCurve cmin, UnityEngine.AnimationCurve cmax, System.UInt32 seed, System.Single minValue, System.Single maxValue) : UnityEngine.AnimationCurve`  

```csharp
private static UnityEngine.AnimationCurve GenCurveFromMinMax(System.Int32 keyCount, UnityEngine.AnimationCurve cmin, UnityEngine.AnimationCurve cmax, System.UInt32 seed, System.Single minValue, System.Single maxValue);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetSeasonAndMidTime(System.Int32 index) : System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single>`  

```csharp
public System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single> GetSeasonAndMidTime(System.Int32 index);
```

- `private GetSeasonMidTime(System.Int32 index) : System.Single`  

```csharp
private System.Single GetSeasonMidTime(System.Int32 index);
```

- `private Intersect(System.Single startTime, System.Single elapsedTime, System.Single seasonStart, System.Single seasonEnd) : System.Boolean`  

```csharp
private System.Boolean Intersect(System.Single startTime, System.Single elapsedTime, System.Single seasonStart, System.Single seasonEnd);
```

- `private static LoopCurve(UnityEngine.AnimationCurve curve, System.Single minValue = 0, System.Single maxValue = 1) : System.Void`  

```csharp
private static System.Void LoopCurve(UnityEngine.AnimationCurve curve, System.Single minValue, System.Single maxValue);
```

- `private RebuildAuroraCurves(System.UInt32 seed) : System.Void`  

```csharp
private System.Void RebuildAuroraCurves(System.UInt32 seed);
```

- `public RebuildCurves() : System.Void`  

```csharp
public System.Void RebuildCurves();
```

- `private RebuildFogCurves(System.UInt32 seed) : System.Void`  

```csharp
private System.Void RebuildFogCurves(System.UInt32 seed);
```

- `private RebuildPrecipitationCurves(System.UInt32 seed) : System.Void`  

```csharp
private System.Void RebuildPrecipitationCurves(System.UInt32 seed);
```

- `private RebuildTemperatureCurves(System.UInt32 seed) : System.Void`  

```csharp
private System.Void RebuildTemperatureCurves(System.UInt32 seed);
```

- `private static SmoothNoise(System.Single x, System.Single y = 0) : System.Single`  

```csharp
private static System.Single SmoothNoise(System.Single x, System.Single y);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.Prefabs.Climate.ClimatePrefab+SeasonTempCurves`  
- `Game.Prefabs.Climate.ClimatePrefab+SeasonPrecipCurves`  
- `Game.Prefabs.Climate.ClimatePrefab+SeasonAuroraCurves`  

