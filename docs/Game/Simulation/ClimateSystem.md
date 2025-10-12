# Game.Simulation.ClimateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPreSerialize`, `Game.Serialization.IPostDeserialize`  

## Fields

- `private Unity.Mathematics.float2 <wind>k__BackingField`  
- `private System.Single <hail>k__BackingField`  
- `public Game.OverridableProperty<System.Single> thunder`  
- `private System.Single <rainbow>k__BackingField`  
- `private System.Single <aerosolDensity>k__BackingField`  
- `private System.Single <seasonTemperature>k__BackingField`  
- `private System.Single <seasonPrecipitation>k__BackingField`  
- `private System.Single <seasonCloudiness>k__BackingField`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem`  
- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  
- `private Unity.Entities.EntityQuery m_ClimateQuery`  
- `private Game.OverridableProperty<System.Single> m_Date`  
- `private readonly Game.OverridableProperty<System.Single> <precipitation>k__BackingField`  
- `private readonly Game.OverridableProperty<System.Single> <temperature>k__BackingField`  
- `private readonly Game.OverridableProperty<System.Single> <cloudiness>k__BackingField`  
- `private readonly Game.OverridableProperty<System.Single> <aurora>k__BackingField`  
- `private readonly Game.OverridableProperty<System.Single> <fog>k__BackingField`  
- `private Unity.Entities.Entity m_CurrentClimate`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_CurrentWeatherEffects`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_NextWeatherEffects`  
- `private System.Single m_TemperatureBaseHeight`  
- `private System.Single <averageTemperature>k__BackingField`  
- `private System.Single <freezingTemperature>k__BackingField`  
- `private Game.Simulation.ClimateSystem+WeatherClassification <classification>k__BackingField`  
- `private Game.Simulation.ClimateSystem+SeasonInfo m_CurrentSeason`  
- `private static readonly System.Int32[] kLut`  
- `private static readonly System.Int32[] kSampleTimes`  

## Properties

- `public Unity.Mathematics.float2 wind { get; private set }`  
- `public System.Single hail { get; set }`  
- `public System.Single rainbow { get; set }`  
- `public System.Single aerosolDensity { get; private set }`  
- `public System.Single seasonTemperature { get; private set }`  
- `public System.Single seasonPrecipitation { get; private set }`  
- `public System.Single seasonCloudiness { get; private set }`  
- `public Game.OverridableProperty<System.Single> currentDate { get }`  
- `public Game.OverridableProperty<System.Single> precipitation { get }`  
- `public Game.OverridableProperty<System.Single> temperature { get }`  
- `public Game.OverridableProperty<System.Single> cloudiness { get }`  
- `public Game.OverridableProperty<System.Single> aurora { get }`  
- `public Game.OverridableProperty<System.Single> fog { get }`  
- `public Unity.Entities.Entity currentClimate { get; set }`  
- `public System.Single temperatureBaseHeight { get }`  
- `public System.Single snowTemperatureHeightScale { get }`  
- `public System.Single averageTemperature { get; private set }`  
- `public System.Single freezingTemperature { get; private set }`  
- `public System.Boolean isRaining { get }`  
- `public System.Boolean isSnowing { get }`  
- `public System.Boolean isPrecipitating { get }`  
- `public Game.Simulation.ClimateSystem+WeatherClassification classification { get; private set }`  
- `public Unity.Entities.Entity currentSeason { get }`  
- `public System.String currentSeasonNameID { get }`  

## Constructors

- `public ClimateSystem()`  

## Methods

- `private <OnCreate>b__100_0() : System.Single`  
- `private ApplyWeatherEffects() : System.Void`  
- `private AreEffectsInvalid(Unity.Collections.NativeList<Unity.Entities.Entity> list) : System.Boolean`  
- `private CalculateMeanCloudiness(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  
- `private CalculateMeanPrecipitation(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  
- `private CalculateMeanTemperature(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  
- `private CalculateMeanTemperatureEkholmModen(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay) : System.Single`  
- `private CalculateMeanTemperatureStandard(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single& meanMin, System.Single& meanMax) : System.Single`  
- `private CalculateTemperatureAverage(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48) : System.Single`  
- `private CalculateTemperatureBaseHeight() : System.Single`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private HandleTriggers() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PatchReferences(Game.Serialization.PrefabReferences& references) : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public PreSerialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private ResetWeatherEffects(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects) : System.Boolean`  
- `public SampleClimate(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single t) : Game.Simulation.ClimateSystem+ClimateSample`  
- `public SampleClimate(System.Single t) : Game.Simulation.ClimateSystem+ClimateSample`  
- `private SelectDefaultWeather(Game.Prefabs.Climate.ClimatePrefab prefab, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentWeathers, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nextWeathers) : System.Boolean`  
- `private SelectRandomWeather(Game.Prefabs.Climate.WeatherPrefab weather, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weathers) : System.Void`  
- `private SelectWeatherPlaceholder(Game.Prefabs.Climate.ClimatePrefab prefab, Game.Prefabs.Climate.WeatherPrefab& current, Game.Prefabs.Climate.WeatherPrefab& next) : System.Boolean`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private SortAndCheckUpdate(Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& reference) : System.Boolean`  
- `private UpdateSeason(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single normalizedDate) : System.Void`  
- `private UpdateWeather(Game.Prefabs.Climate.ClimatePrefab prefab) : System.Void`  

## Nested types

- `Game.Simulation.ClimateSystem+SeasonInfo`  
- `Game.Simulation.ClimateSystem+WeatherClassification`  
- `Game.Simulation.ClimateSystem+ClimateSample`  
- `Game.Simulation.ClimateSystem+WeatherTempData`  

