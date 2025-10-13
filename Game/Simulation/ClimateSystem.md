# Game.Simulation.ClimateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPreSerialize`, `Game.Serialization.IPostDeserialize`  

## Code

```csharp
public class ClimateSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPreSerialize, Game.Serialization.IPostDeserialize
{
    private Unity.Mathematics.float2 <wind>k__BackingField;
    private System.Single <hail>k__BackingField;
    public Game.OverridableProperty<System.Single> thunder;
    private System.Single <rainbow>k__BackingField;
    private System.Single <aerosolDensity>k__BackingField;
    private System.Single <seasonTemperature>k__BackingField;
    private System.Single <seasonPrecipitation>k__BackingField;
    private System.Single <seasonCloudiness>k__BackingField;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem;
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Unity.Entities.EntityQuery m_ClimateQuery;
    private Game.OverridableProperty<System.Single> m_Date;
    private readonly Game.OverridableProperty<System.Single> <precipitation>k__BackingField;
    private readonly Game.OverridableProperty<System.Single> <temperature>k__BackingField;
    private readonly Game.OverridableProperty<System.Single> <cloudiness>k__BackingField;
    private readonly Game.OverridableProperty<System.Single> <aurora>k__BackingField;
    private readonly Game.OverridableProperty<System.Single> <fog>k__BackingField;
    private Unity.Entities.Entity m_CurrentClimate;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_CurrentWeatherEffects;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_NextWeatherEffects;
    private System.Single m_TemperatureBaseHeight;
    private System.Single <averageTemperature>k__BackingField;
    private System.Single <freezingTemperature>k__BackingField;
    private Game.Simulation.ClimateSystem+WeatherClassification <classification>k__BackingField;
    private Game.Simulation.ClimateSystem+SeasonInfo m_CurrentSeason;
    private static readonly System.Int32[] kLut;
    private static readonly System.Int32[] kSampleTimes;

    public Unity.Mathematics.float2 wind { get; private set; }
    public System.Single hail { get; set; }
    public System.Single rainbow { get; set; }
    public System.Single aerosolDensity { get; private set; }
    public System.Single seasonTemperature { get; private set; }
    public System.Single seasonPrecipitation { get; private set; }
    public System.Single seasonCloudiness { get; private set; }
    public Game.OverridableProperty<System.Single> currentDate { get; }
    public Game.OverridableProperty<System.Single> precipitation { get; }
    public Game.OverridableProperty<System.Single> temperature { get; }
    public Game.OverridableProperty<System.Single> cloudiness { get; }
    public Game.OverridableProperty<System.Single> aurora { get; }
    public Game.OverridableProperty<System.Single> fog { get; }
    public Unity.Entities.Entity currentClimate { get; set; }
    public System.Single temperatureBaseHeight { get; }
    public System.Single snowTemperatureHeightScale { get; }
    public System.Single averageTemperature { get; private set; }
    public System.Single freezingTemperature { get; private set; }
    public System.Boolean isRaining { get; }
    public System.Boolean isSnowing { get; }
    public System.Boolean isPrecipitating { get; }
    public Game.Simulation.ClimateSystem+WeatherClassification classification { get; private set; }
    public Unity.Entities.Entity currentSeason { get; }
    public System.String currentSeasonNameID { get; }

    public ClimateSystem();

    private System.Single <OnCreate>b__100_0();
    private System.Void ApplyWeatherEffects();
    private System.Boolean AreEffectsInvalid(Unity.Collections.NativeList<Unity.Entities.Entity> list);
    private System.Single CalculateMeanCloudiness(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single startRange, System.Single endRange);
    private System.Single CalculateMeanPrecipitation(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single startRange, System.Single endRange);
    private System.Single CalculateMeanTemperature(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single startRange, System.Single endRange);
    private System.Single CalculateMeanTemperatureEkholmModen(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay);
    private System.Single CalculateMeanTemperatureStandard(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single& meanMin, System.Single& meanMax);
    private System.Single CalculateTemperatureAverage(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay);
    private System.Single CalculateTemperatureBaseHeight();
    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void HandleTriggers();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PatchReferences(Game.Serialization.PrefabReferences& references);
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void PreSerialize(Colossal.Serialization.Entities.Context context);
    private System.Boolean ResetWeatherEffects(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects);
    public Game.Simulation.ClimateSystem+ClimateSample SampleClimate(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single t);
    public Game.Simulation.ClimateSystem+ClimateSample SampleClimate(System.Single t);
    private System.Boolean SelectDefaultWeather(Game.Prefabs.Climate.ClimatePrefab prefab, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentWeathers, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nextWeathers);
    private System.Void SelectRandomWeather(Game.Prefabs.Climate.WeatherPrefab weather, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weathers);
    private System.Boolean SelectWeatherPlaceholder(Game.Prefabs.Climate.ClimatePrefab prefab, Game.Prefabs.Climate.WeatherPrefab& current, Game.Prefabs.Climate.WeatherPrefab& next);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Boolean SortAndCheckUpdate(Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& reference);
    private System.Void UpdateSeason(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single normalizedDate);
    private System.Void UpdateWeather(Game.Prefabs.Climate.ClimatePrefab prefab);
}
```


## Fields

- `private Unity.Mathematics.float2 <wind>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <wind>k__BackingField;
```

- `private System.Single <hail>k__BackingField`  

```csharp
private System.Single <hail>k__BackingField;
```

- `public Game.OverridableProperty<System.Single> thunder`  

```csharp
public Game.OverridableProperty<System.Single> thunder;
```

- `private System.Single <rainbow>k__BackingField`  

```csharp
private System.Single <rainbow>k__BackingField;
```

- `private System.Single <aerosolDensity>k__BackingField`  

```csharp
private System.Single <aerosolDensity>k__BackingField;
```

- `private System.Single <seasonTemperature>k__BackingField`  

```csharp
private System.Single <seasonTemperature>k__BackingField;
```

- `private System.Single <seasonPrecipitation>k__BackingField`  

```csharp
private System.Single <seasonPrecipitation>k__BackingField;
```

- `private System.Single <seasonCloudiness>k__BackingField`  

```csharp
private System.Single <seasonCloudiness>k__BackingField;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem`  

```csharp
private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem;
```

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Unity.Entities.EntityQuery m_ClimateQuery`  

```csharp
private Unity.Entities.EntityQuery m_ClimateQuery;
```

- `private Game.OverridableProperty<System.Single> m_Date`  

```csharp
private Game.OverridableProperty<System.Single> m_Date;
```

- `private readonly Game.OverridableProperty<System.Single> <precipitation>k__BackingField`  

```csharp
private readonly Game.OverridableProperty<System.Single> <precipitation>k__BackingField;
```

- `private readonly Game.OverridableProperty<System.Single> <temperature>k__BackingField`  

```csharp
private readonly Game.OverridableProperty<System.Single> <temperature>k__BackingField;
```

- `private readonly Game.OverridableProperty<System.Single> <cloudiness>k__BackingField`  

```csharp
private readonly Game.OverridableProperty<System.Single> <cloudiness>k__BackingField;
```

- `private readonly Game.OverridableProperty<System.Single> <aurora>k__BackingField`  

```csharp
private readonly Game.OverridableProperty<System.Single> <aurora>k__BackingField;
```

- `private readonly Game.OverridableProperty<System.Single> <fog>k__BackingField`  

```csharp
private readonly Game.OverridableProperty<System.Single> <fog>k__BackingField;
```

- `private Unity.Entities.Entity m_CurrentClimate`  

```csharp
private Unity.Entities.Entity m_CurrentClimate;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_CurrentWeatherEffects`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_CurrentWeatherEffects;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_NextWeatherEffects`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_NextWeatherEffects;
```

- `private System.Single m_TemperatureBaseHeight`  

```csharp
private System.Single m_TemperatureBaseHeight;
```

- `private System.Single <averageTemperature>k__BackingField`  

```csharp
private System.Single <averageTemperature>k__BackingField;
```

- `private System.Single <freezingTemperature>k__BackingField`  

```csharp
private System.Single <freezingTemperature>k__BackingField;
```

- `private Game.Simulation.ClimateSystem+WeatherClassification <classification>k__BackingField`  

```csharp
private Game.Simulation.ClimateSystem+WeatherClassification <classification>k__BackingField;
```

- `private Game.Simulation.ClimateSystem+SeasonInfo m_CurrentSeason`  

```csharp
private Game.Simulation.ClimateSystem+SeasonInfo m_CurrentSeason;
```

- `private static readonly System.Int32[] kLut`  

```csharp
private static readonly System.Int32[] kLut;
```

- `private static readonly System.Int32[] kSampleTimes`  

```csharp
private static readonly System.Int32[] kSampleTimes;
```


## Properties

- `public Unity.Mathematics.float2 wind { get; private set }`  

```csharp
public Unity.Mathematics.float2 wind { get; private set; }
```

- `public System.Single hail { get; set }`  

```csharp
public System.Single hail { get; set; }
```

- `public System.Single rainbow { get; set }`  

```csharp
public System.Single rainbow { get; set; }
```

- `public System.Single aerosolDensity { get; private set }`  

```csharp
public System.Single aerosolDensity { get; private set; }
```

- `public System.Single seasonTemperature { get; private set }`  

```csharp
public System.Single seasonTemperature { get; private set; }
```

- `public System.Single seasonPrecipitation { get; private set }`  

```csharp
public System.Single seasonPrecipitation { get; private set; }
```

- `public System.Single seasonCloudiness { get; private set }`  

```csharp
public System.Single seasonCloudiness { get; private set; }
```

- `public Game.OverridableProperty<System.Single> currentDate { get }`  

```csharp
public Game.OverridableProperty<System.Single> currentDate { get; }
```

- `public Game.OverridableProperty<System.Single> precipitation { get }`  

```csharp
public Game.OverridableProperty<System.Single> precipitation { get; }
```

- `public Game.OverridableProperty<System.Single> temperature { get }`  

```csharp
public Game.OverridableProperty<System.Single> temperature { get; }
```

- `public Game.OverridableProperty<System.Single> cloudiness { get }`  

```csharp
public Game.OverridableProperty<System.Single> cloudiness { get; }
```

- `public Game.OverridableProperty<System.Single> aurora { get }`  

```csharp
public Game.OverridableProperty<System.Single> aurora { get; }
```

- `public Game.OverridableProperty<System.Single> fog { get }`  

```csharp
public Game.OverridableProperty<System.Single> fog { get; }
```

- `public Unity.Entities.Entity currentClimate { get; set }`  

```csharp
public Unity.Entities.Entity currentClimate { get; set; }
```

- `public System.Single temperatureBaseHeight { get }`  

```csharp
public System.Single temperatureBaseHeight { get; }
```

- `public System.Single snowTemperatureHeightScale { get }`  

```csharp
public System.Single snowTemperatureHeightScale { get; }
```

- `public System.Single averageTemperature { get; private set }`  

```csharp
public System.Single averageTemperature { get; private set; }
```

- `public System.Single freezingTemperature { get; private set }`  

```csharp
public System.Single freezingTemperature { get; private set; }
```

- `public System.Boolean isRaining { get }`  

```csharp
public System.Boolean isRaining { get; }
```

- `public System.Boolean isSnowing { get }`  

```csharp
public System.Boolean isSnowing { get; }
```

- `public System.Boolean isPrecipitating { get }`  

```csharp
public System.Boolean isPrecipitating { get; }
```

- `public Game.Simulation.ClimateSystem+WeatherClassification classification { get; private set }`  

```csharp
public Game.Simulation.ClimateSystem+WeatherClassification classification { get; private set; }
```

- `public Unity.Entities.Entity currentSeason { get }`  

```csharp
public Unity.Entities.Entity currentSeason { get; }
```

- `public System.String currentSeasonNameID { get }`  

```csharp
public System.String currentSeasonNameID { get; }
```


## Constructors

- `public ClimateSystem()`  

```csharp
public ClimateSystem();
```


## Methods

- `private <OnCreate>b__100_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__100_0();
```

- `private ApplyWeatherEffects() : System.Void`  

```csharp
private System.Void ApplyWeatherEffects();
```

- `private AreEffectsInvalid(Unity.Collections.NativeList<Unity.Entities.Entity> list) : System.Boolean`  

```csharp
private System.Boolean AreEffectsInvalid(Unity.Collections.NativeList<Unity.Entities.Entity> list);
```

- `private CalculateMeanCloudiness(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  

```csharp
private System.Single CalculateMeanCloudiness(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single startRange, System.Single endRange);
```

- `private CalculateMeanPrecipitation(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  

```csharp
private System.Single CalculateMeanPrecipitation(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single startRange, System.Single endRange);
```

- `private CalculateMeanTemperature(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  

```csharp
private System.Single CalculateMeanTemperature(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single startRange, System.Single endRange);
```

- `private CalculateMeanTemperatureEkholmModen(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay) : System.Single`  

```csharp
private System.Single CalculateMeanTemperatureEkholmModen(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay);
```

- `private CalculateMeanTemperatureStandard(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single& meanMin, System.Single& meanMax) : System.Single`  

```csharp
private System.Single CalculateMeanTemperatureStandard(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single& meanMin, System.Single& meanMax);
```

- `private CalculateTemperatureAverage(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48) : System.Single`  

```csharp
private System.Single CalculateTemperatureAverage(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay);
```

- `private CalculateTemperatureBaseHeight() : System.Single`  

```csharp
private System.Single CalculateTemperatureBaseHeight();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private HandleTriggers() : System.Void`  

```csharp
private System.Void HandleTriggers();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PatchReferences(Game.Serialization.PrefabReferences& references) : System.Void`  

```csharp
public System.Void PatchReferences(Game.Serialization.PrefabReferences& references);
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public PreSerialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreSerialize(Colossal.Serialization.Entities.Context context);
```

- `private ResetWeatherEffects(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects) : System.Boolean`  

```csharp
private System.Boolean ResetWeatherEffects(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects);
```

- `public SampleClimate(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single t) : Game.Simulation.ClimateSystem+ClimateSample`  

```csharp
public Game.Simulation.ClimateSystem+ClimateSample SampleClimate(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single t);
```

- `public SampleClimate(System.Single t) : Game.Simulation.ClimateSystem+ClimateSample`  

```csharp
public Game.Simulation.ClimateSystem+ClimateSample SampleClimate(System.Single t);
```

- `private SelectDefaultWeather(Game.Prefabs.Climate.ClimatePrefab prefab, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentWeathers, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nextWeathers) : System.Boolean`  

```csharp
private System.Boolean SelectDefaultWeather(Game.Prefabs.Climate.ClimatePrefab prefab, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentWeathers, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nextWeathers);
```

- `private SelectRandomWeather(Game.Prefabs.Climate.WeatherPrefab weather, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weathers) : System.Void`  

```csharp
private System.Void SelectRandomWeather(Game.Prefabs.Climate.WeatherPrefab weather, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weathers);
```

- `private SelectWeatherPlaceholder(Game.Prefabs.Climate.ClimatePrefab prefab, Game.Prefabs.Climate.WeatherPrefab& current, Game.Prefabs.Climate.WeatherPrefab& next) : System.Boolean`  

```csharp
private System.Boolean SelectWeatherPlaceholder(Game.Prefabs.Climate.ClimatePrefab prefab, Game.Prefabs.Climate.WeatherPrefab& current, Game.Prefabs.Climate.WeatherPrefab& next);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private SortAndCheckUpdate(Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& reference) : System.Boolean`  

```csharp
private System.Boolean SortAndCheckUpdate(Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& reference);
```

- `private UpdateSeason(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single normalizedDate) : System.Void`  

```csharp
private System.Void UpdateSeason(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single normalizedDate);
```

- `private UpdateWeather(Game.Prefabs.Climate.ClimatePrefab prefab) : System.Void`  

```csharp
private System.Void UpdateWeather(Game.Prefabs.Climate.ClimatePrefab prefab);
```


## Nested types

- `Game.Simulation.ClimateSystem+SeasonInfo`  
- `Game.Simulation.ClimateSystem+WeatherClassification`  
- `Game.Simulation.ClimateSystem+ClimateSample`  
- `Game.Simulation.ClimateSystem+WeatherTempData`  

