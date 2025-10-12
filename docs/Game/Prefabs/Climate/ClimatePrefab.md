# Game.Prefabs.Climate.ClimatePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_Latitude`  
- `public System.Single m_Longitude`  
- `public System.Single m_FreezingTemperature`  
- `public UnityEngine.AnimationCurve m_Temperature`  
- `public UnityEngine.AnimationCurve m_Precipitation`  
- `public UnityEngine.AnimationCurve m_Cloudiness`  
- `public UnityEngine.AnimationCurve m_Aurora`  
- `public UnityEngine.AnimationCurve m_Fog`  
- `public Game.Prefabs.Climate.WeatherPrefab m_DefaultWeather`  
- `public Game.Prefabs.Climate.WeatherPrefab[] m_DefaultWeathers`  
- `public Game.Simulation.ClimateSystem+SeasonInfo[] m_Seasons`  
- `public System.Int32 m_RandomSeed`  
- `private System.Int32[] m_SeasonsOrder`  
- `public static const System.Int32 kYearDuration`  
- `private static const System.Single k90PercentileToStdDev`  

## Properties

- `public Colossal.Mathematics.Bounds1 temperatureRange { get }`  
- `public System.Single averageCloudiness { get }`  
- `public System.Single averagePrecipitation { get }`  

## Constructors

- `public ClimatePrefab()`  

## Methods

- `private <EnsureSeasonsOrder>b__16_0(System.Int32 v) : System.Single`  
- `public CountElapsedSeasons(System.Single startTime, System.Single elapsedTime) : System.Int32`  
- `public CreateSeasonAuroraCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonAuroraCurves`  
- `public CreateSeasonPrecipCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonPrecipCurves`  
- `public CreateSeasonTemperatureCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonTempCurves`  
- `internal EnsureSeasonsOrder(System.Boolean force = False) : System.Void`  
- `public FindSeasonByTime(System.Single time) : System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single, System.Single>`  
- `private static GaussianRandom(System.Single mean, System.Single dev, Unity.Mathematics.Random& rng) : System.Single`  
- `private static GenCurveFromMinMax(System.Int32 keyCount, UnityEngine.AnimationCurve cmin, UnityEngine.AnimationCurve cmax, System.UInt32 seed, System.Single minValue, System.Single maxValue) : UnityEngine.AnimationCurve`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetSeasonAndMidTime(System.Int32 index) : System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single>`  
- `private GetSeasonMidTime(System.Int32 index) : System.Single`  
- `private Intersect(System.Single startTime, System.Single elapsedTime, System.Single seasonStart, System.Single seasonEnd) : System.Boolean`  
- `private static LoopCurve(UnityEngine.AnimationCurve curve, System.Single minValue = 0, System.Single maxValue = 1) : System.Void`  
- `private RebuildAuroraCurves(System.UInt32 seed) : System.Void`  
- `public RebuildCurves() : System.Void`  
- `private RebuildFogCurves(System.UInt32 seed) : System.Void`  
- `private RebuildPrecipitationCurves(System.UInt32 seed) : System.Void`  
- `private RebuildTemperatureCurves(System.UInt32 seed) : System.Void`  
- `private static SmoothNoise(System.Single x, System.Single y = 0) : System.Single`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.Prefabs.Climate.ClimatePrefab+SeasonTempCurves`  
- `Game.Prefabs.Climate.ClimatePrefab+SeasonPrecipCurves`  
- `Game.Prefabs.Climate.ClimatePrefab+SeasonAuroraCurves`  

