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
[Preserve]
	public ClimateSystem()
	{
	}
```


## Methods

- `private <OnCreate>b__100_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__100_0();
```

- `private ApplyWeatherEffects() : System.Void`  

```csharp
private void ApplyWeatherEffects()
	{
		m_ClimateRenderSystem.Clear();
		for (int i = 0; i < m_CurrentWeatherEffects.Length; i++)
		{
			WeatherPrefab prefab = m_PrefabSystem.GetPrefab<WeatherPrefab>(m_CurrentWeatherEffects[i]);
			if (prefab.m_Classification != WeatherClassification.Irrelevant)
			{
				classification = prefab.m_Classification;
			}
			m_ClimateRenderSystem.ScheduleFrom(prefab);
		}
		for (int j = 0; j < m_NextWeatherEffects.Length; j++)
		{
			WeatherPrefab prefab2 = m_PrefabSystem.GetPrefab<WeatherPrefab>(m_NextWeatherEffects[j]);
			if (prefab2.m_Classification != WeatherClassification.Irrelevant)
			{
				classification = prefab2.m_Classification;
			}
			m_ClimateRenderSystem.ScheduleTo(prefab2);
		}
	}
```

- `private AreEffectsInvalid(Unity.Collections.NativeList<Unity.Entities.Entity> list) : System.Boolean`  

```csharp
private bool AreEffectsInvalid(NativeList<Entity> list)
	{
		for (int i = 0; i < list.Length; i++)
		{
			if (list[i] == Entity.Null)
			{
				list.ResizeUninitialized(0);
				return true;
			}
		}
		return false;
	}
```

- `private CalculateMeanCloudiness(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  

```csharp
private float CalculateMeanCloudiness(ClimatePrefab prefab, int resolutionPerDay = 48, float startRange = 0f, float endRange = 1f)
	{
		int daysPerYear = m_TimeSystem.daysPerYear;
		float num = startRange * (float)daysPerYear;
		float num2 = endRange * (float)daysPerYear;
		int num3 = (int)math.round((num2 - num) * (float)resolutionPerDay);
		float num4 = 0f;
		for (int i = 0; i < num3; i++)
		{
			float t = (float)i / (float)num3;
			num4 += prefab.m_Cloudiness.Evaluate(math.lerp(num, num2, t));
		}
		return num4 / (float)num3;
	}
```

- `private CalculateMeanPrecipitation(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  

```csharp
private float CalculateMeanPrecipitation(ClimatePrefab prefab, int resolutionPerDay = 48, float startRange = 0f, float endRange = 1f)
	{
		int daysPerYear = m_TimeSystem.daysPerYear;
		float num = startRange * (float)daysPerYear;
		float num2 = endRange * (float)daysPerYear;
		int num3 = (int)math.round((num2 - num) * (float)resolutionPerDay);
		float num4 = 0f;
		for (int i = 0; i < num3; i++)
		{
			float t = (float)i / (float)num3;
			num4 += prefab.m_Precipitation.Evaluate(math.lerp(num, num2, t));
		}
		return num4 / (float)num3;
	}
```

- `private CalculateMeanTemperature(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48, System.Single startRange = 0, System.Single endRange = 1) : System.Single`  

```csharp
private float CalculateMeanTemperature(ClimatePrefab prefab, int resolutionPerDay = 48, float startRange = 0f, float endRange = 1f)
	{
		int daysPerYear = m_TimeSystem.daysPerYear;
		float num = startRange * (float)daysPerYear;
		float num2 = endRange * (float)daysPerYear;
		int num3 = (int)math.round((num2 - num) * (float)resolutionPerDay);
		float2 zero = float2.zero;
		for (int i = 0; i < num3; i++)
		{
			float t = (float)i / (float)num3;
			float y = prefab.m_Temperature.Evaluate(math.lerp(num, num2, t));
			zero.x = math.min(zero.x, y);
			zero.y = math.max(zero.y, y);
		}
		return (zero.x + zero.y) * 0.5f;
	}
```

- `private CalculateMeanTemperatureEkholmModen(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay) : System.Single`  

```csharp
private float CalculateMeanTemperatureEkholmModen(ClimatePrefab prefab, int resolutionPerDay)
	{
		Assert.AreEqual(12, m_TimeSystem.daysPerYear);
		if (prefab.m_Seasons != null)
		{
			int daysPerYear = m_TimeSystem.daysPerYear;
			int num = daysPerYear + (kSampleTimes.Length + 2);
			float num2 = 0f;
			for (int i = 0; i < daysPerYear; i++)
			{
				float num3 = 0f;
				for (int j = 0; j < kSampleTimes.Length; j++)
				{
					float time = (float)(kSampleTimes[j] + i) / (float)num * (float)daysPerYear;
					float num4 = prefab.m_Temperature.Evaluate(time);
					num3 += num4 * (float)kLut[i, j];
				}
				float2 zero = float2.zero;
				for (int k = 0; k < resolutionPerDay; k++)
				{
					float time2 = (float)(i + k - 5) / (float)num * (float)daysPerYear;
					float y = prefab.m_Temperature.Evaluate(time2);
					zero.x = math.min(zero.x, y);
					zero.y = math.max(zero.y, y);
				}
				num3 += zero.x * (float)kLut[i, 3];
				num3 += zero.y * (float)kLut[i, 3];
				num2 += num3 / 100f;
			}
			return num2 / (float)m_TimeSystem.daysPerYear;
		}
		return 0f;
	}
```

- `private CalculateMeanTemperatureStandard(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay, System.Single& meanMin, System.Single& meanMax) : System.Single`  

```csharp
private float CalculateMeanTemperatureStandard(ClimatePrefab prefab, int resolutionPerDay, out float meanMin, out float meanMax)
	{
		if (prefab.m_Seasons != null)
		{
			int length = prefab.m_Temperature.length;
			int num = m_TimeSystem.daysPerYear * resolutionPerDay;
			float2 zero = float2.zero;
			for (int i = 0; i < m_TimeSystem.daysPerYear; i++)
			{
				float2 zero2 = float2.zero;
				for (int j = 0; j < resolutionPerDay; j++)
				{
					float time = (float)(i + j) / (float)num * (float)length;
					float y = prefab.m_Temperature.Evaluate(time);
					zero2.x = math.min(zero2.x, y);
					zero2.y = math.max(zero2.y, y);
				}
				zero += zero2;
			}
			float2 @float = zero / m_TimeSystem.daysPerYear;
			meanMin = @float.x;
			meanMax = @float.y;
			return (@float.x + @float.y) * 0.5f;
		}
		meanMin = 0f;
		meanMax = 0f;
		return 0f;
	}
```

- `private CalculateTemperatureAverage(Game.Prefabs.Climate.ClimatePrefab prefab, System.Int32 resolutionPerDay = 48) : System.Single`  

```csharp
private float CalculateTemperatureAverage(ClimatePrefab prefab, int resolutionPerDay = 48)
	{
		freezingTemperature = prefab.m_FreezingTemperature;
		if (m_TimeSystem.daysPerYear == 12)
		{
			return CalculateMeanTemperatureEkholmModen(prefab, resolutionPerDay);
		}
		float meanMin;
		float meanMax;
		return CalculateMeanTemperatureStandard(prefab, resolutionPerDay, out meanMin, out meanMax);
	}
```

- `private CalculateTemperatureBaseHeight() : System.Single`  

```csharp
private float CalculateTemperatureBaseHeight()
	{
		TerrainSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		WaterSystem orCreateSystemManaged2 = base.World.GetOrCreateSystemManaged<WaterSystem>();
		MapTileSystem orCreateSystemManaged3 = base.World.GetOrCreateSystemManaged<MapTileSystem>();
		TerrainHeightData terrainData = orCreateSystemManaged.GetHeightData();
		JobHandle deps;
		WaterSurfaceData data = orCreateSystemManaged2.GetSurfaceData(out deps);
		deps.Complete();
		NativeList<Entity> startTiles = orCreateSystemManaged3.GetStartTiles();
		float num = 0f;
		float num2 = 0f;
		for (int i = 0; i < startTiles.Length; i++)
		{
			if (base.EntityManager.TryGetBuffer(startTiles[i], isReadOnly: true, out DynamicBuffer<Node> buffer))
			{
				for (int j = 0; j < buffer.Length; j++)
				{
					num += WaterUtils.SampleHeight(ref data, ref terrainData, buffer[j].m_Position);
					num2 += 1f;
				}
			}
		}
		if (!(num2 > 0f))
		{
			return 0f;
		}
		return num / num2;
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private HandleTriggers() : System.Void`  

```csharp
private void HandleTriggers()
	{
		NativeQueue<TriggerAction> nativeQueue = m_TriggerSystem.CreateActionBuffer();
		nativeQueue.Enqueue(new TriggerAction(TriggerType.Temperature, Entity.Null, temperature));
		bool flag = hail > 0.001f;
		bool flag2 = classification == WeatherClassification.Overcast;
		bool flag3 = m_TimeSystem.normalizedTime >= EffectFlagSystem.kDayBegin && m_TimeSystem.normalizedTime < EffectFlagSystem.kNightBegin;
		bool flag4 = classification == WeatherClassification.Stormy;
		if (flag || flag4)
		{
			nativeQueue.Enqueue(new TriggerAction(TriggerType.WeatherStormy, Entity.Null, 0f));
		}
		else if (!flag && isRaining)
		{
			nativeQueue.Enqueue(new TriggerAction(((float)temperature > 0f) ? TriggerType.WeatherRainy : TriggerType.WeatherSnowy, Entity.Null, 0f));
		}
		else if (!flag && !isRaining && !flag2 && flag3)
		{
			nativeQueue.Enqueue(new TriggerAction(((float)temperature > 15f) ? TriggerType.WeatherSunny : TriggerType.WeatherClear, Entity.Null, 0f));
		}
		else if (flag2)
		{
			nativeQueue.Enqueue(new TriggerAction(TriggerType.WeatherCloudy, Entity.Null, 0f));
		}
		if (!flag3)
		{
			nativeQueue.Enqueue(new TriggerAction(TriggerType.AuroraBorealis, Entity.Null, aurora));
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_ClimateRenderSystem = base.World.GetOrCreateSystemManaged<ClimateRenderSystem>();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_CurrentWeatherEffects = new NativeList<Entity>(0, Allocator.Persistent);
		m_NextWeatherEffects = new NativeList<Entity>(0, Allocator.Persistent);
		m_ClimateQuery = GetEntityQuery(ComponentType.ReadOnly<ClimateData>());
		m_Date = new OverridableProperty<float>(() => m_TimeSystem.normalizedDate);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		m_CurrentWeatherEffects.Dispose();
		m_NextWeatherEffects.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (currentClimate != Entity.Null)
		{
			ClimatePrefab prefab = m_PrefabSystem.GetPrefab<ClimatePrefab>(currentClimate);
			ClimateSample climateSample = SampleClimate(prefab, m_Date);
			temperature.value = climateSample.temperature;
			precipitation.value = climateSample.precipitation;
			cloudiness.value = climateSample.cloudiness;
			aurora.value = climateSample.aurora;
			fog.value = climateSample.fog;
			UpdateSeason(prefab, m_Date);
			UpdateWeather(prefab);
		}
		if (m_TriggerSystem.Enabled)
		{
			HandleTriggers();
		}
	}
```

- `public PatchReferences(Game.Serialization.PrefabReferences& references) : System.Void`  

```csharp
public void PatchReferences(ref PrefabReferences references)
	{
		m_CurrentClimate = references.Check(base.EntityManager, m_CurrentClimate);
		for (int i = 0; i < m_CurrentWeatherEffects.Length; i++)
		{
			m_CurrentWeatherEffects[i] = references.Check(base.EntityManager, m_CurrentWeatherEffects[i]);
		}
		for (int j = 0; j < m_NextWeatherEffects.Length; j++)
		{
			m_NextWeatherEffects[j] = references.Check(base.EntityManager, m_NextWeatherEffects[j]);
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (m_CurrentClimate == Entity.Null || !m_PrefabSystem.TryGetPrefab<ClimatePrefab>(m_CurrentClimate, out var _))
		{
			if (m_CurrentClimate != Entity.Null)
			{
				COSystemBase.baseLog.Error("Missing climate prefab, reverting to default climate");
			}
			using NativeArray<Entity> nativeArray = m_ClimateQuery.ToEntityArray(Allocator.TempJob);
			if (nativeArray.Length > 0)
			{
				m_CurrentClimate = nativeArray[0];
			}
		}
		if (m_CurrentClimate != Entity.Null)
		{
			ClimatePrefab prefab2 = m_PrefabSystem.GetPrefab<ClimatePrefab>(m_CurrentClimate);
			prefab2.EnsureSeasonsOrder(force: true);
			averageTemperature = CalculateTemperatureAverage(prefab2);
			UpdateSeason(prefab2, m_Date);
			if (AreEffectsInvalid(m_CurrentWeatherEffects) || m_CurrentWeatherEffects.Length == 0 || AreEffectsInvalid(m_NextWeatherEffects) || m_NextWeatherEffects.Length == 0)
			{
				UpdateWeather(prefab2);
			}
			else
			{
				ApplyWeatherEffects();
			}
			m_PlanetarySystem.latitude = prefab2.m_Latitude;
			m_PlanetarySystem.longitude = prefab2.m_Longitude;
		}
	}
```

- `public PreSerialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreSerialize(Context context)
	{
		if (context.purpose == Purpose.SaveMap)
		{
			m_TemperatureBaseHeight = CalculateTemperatureBaseHeight();
		}
	}
```

- `private ResetWeatherEffects(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects) : System.Boolean`  

```csharp
private bool ResetWeatherEffects(ref NativeList<Entity> weatherEffects)
	{
		bool result = weatherEffects.Length != 0;
		weatherEffects.Clear();
		return result;
	}
```

- `public SampleClimate(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single t) : Game.Simulation.ClimateSystem+ClimateSample`  

```csharp
public ClimateSample SampleClimate(float t)
	{
		if (m_CurrentClimate != Entity.Null)
		{
			ClimatePrefab prefab = m_PrefabSystem.GetPrefab<ClimatePrefab>(m_CurrentClimate);
			ClimateSample result = SampleClimate(prefab, t);
			if (temperature.overrideState)
			{
				result.temperature = temperature.overrideValue;
			}
			if (precipitation.overrideState)
			{
				result.precipitation = precipitation.overrideValue;
			}
			if (cloudiness.overrideState)
			{
				result.cloudiness = cloudiness.overrideValue;
			}
			if (aurora.overrideState)
			{
				result.aurora = aurora.overrideValue;
			}
			if (fog.overrideState)
			{
				result.fog = fog.overrideValue;
			}
			return result;
		}
		return default(ClimateSample);
	}
```

- `public SampleClimate(System.Single t) : Game.Simulation.ClimateSystem+ClimateSample`  

```csharp
public ClimateSample SampleClimate(float t)
	{
		if (m_CurrentClimate != Entity.Null)
		{
			ClimatePrefab prefab = m_PrefabSystem.GetPrefab<ClimatePrefab>(m_CurrentClimate);
			ClimateSample result = SampleClimate(prefab, t);
			if (temperature.overrideState)
			{
				result.temperature = temperature.overrideValue;
			}
			if (precipitation.overrideState)
			{
				result.precipitation = precipitation.overrideValue;
			}
			if (cloudiness.overrideState)
			{
				result.cloudiness = cloudiness.overrideValue;
			}
			if (aurora.overrideState)
			{
				result.aurora = aurora.overrideValue;
			}
			if (fog.overrideState)
			{
				result.fog = fog.overrideValue;
			}
			return result;
		}
		return default(ClimateSample);
	}
```

- `private SelectDefaultWeather(Game.Prefabs.Climate.ClimatePrefab prefab, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentWeathers, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nextWeathers) : System.Boolean`  

```csharp
private bool SelectDefaultWeather(ClimatePrefab prefab, ref NativeList<WeatherTempData> currentWeathers, ref NativeList<WeatherTempData> nextWeathers)
	{
		if (prefab.m_DefaultWeather != null)
		{
			WeatherTempData value = new WeatherTempData
			{
				m_Entity = m_PrefabSystem.GetEntity(prefab.m_DefaultWeather),
				m_Priority = -1001f
			};
			currentWeathers.Add(in value);
			nextWeathers.Add(in value);
			return true;
		}
		return false;
	}
```

- `private SelectRandomWeather(Game.Prefabs.Climate.WeatherPrefab weather, Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weathers) : System.Void`  

```csharp
private void SelectRandomWeather(WeatherPrefab weather, ref NativeList<WeatherTempData> weathers)
	{
		WeatherTempData value = default(WeatherTempData);
		value.m_Entity = m_PrefabSystem.GetEntity(weather);
		value.m_Priority = -1000f;
		weathers.Add(in value);
		if (!base.EntityManager.TryGetBuffer(value.m_Entity, isReadOnly: true, out DynamicBuffer<PlaceholderObjectElement> buffer))
		{
			return;
		}
		WeatherTempData value2 = default(WeatherTempData);
		for (int i = 0; i < buffer.Length; i++)
		{
			value2.m_Entity = buffer[i].m_Object;
			value2.m_Priority = 0f;
			if (base.EntityManager.TryGetBuffer(value2.m_Entity, isReadOnly: true, out DynamicBuffer<ObjectRequirementElement> buffer2))
			{
				int num = -1;
				bool flag = true;
				for (int j = 0; j < buffer2.Length; j++)
				{
					ObjectRequirementElement objectRequirementElement = buffer2[j];
					if ((objectRequirementElement.m_Type & ObjectRequirementType.SelectOnly) != 0)
					{
						continue;
					}
					if (objectRequirementElement.m_Group != num)
					{
						if (!flag)
						{
							break;
						}
						num = objectRequirementElement.m_Group;
						flag = false;
					}
					flag |= objectRequirementElement.m_Requirement == currentSeason;
					value2.m_Priority = 1000f;
				}
				if (!flag)
				{
					continue;
				}
			}
			WeatherPrefab prefab = m_PrefabSystem.GetPrefab<WeatherPrefab>(value2.m_Entity);
			if ((float)aurora > 0f && prefab.m_RandomizationLayer == WeatherPrefab.RandomizationLayer.Aurora)
			{
				value2.m_Priority = 500f;
				weathers.Add(in value2);
			}
			else if (prefab.m_RandomizationLayer == WeatherPrefab.RandomizationLayer.Cloudiness)
			{
				value2.m_Priority = 250f;
				weathers.Add(in value2);
			}
			else if (prefab.m_RandomizationLayer == WeatherPrefab.RandomizationLayer.Season)
			{
				value2.m_Priority = 300f;
				weathers.Add(in value2);
			}
		}
	}
```

- `private SelectWeatherPlaceholder(Game.Prefabs.Climate.ClimatePrefab prefab, Game.Prefabs.Climate.WeatherPrefab& current, Game.Prefabs.Climate.WeatherPrefab& next) : System.Boolean`  

```csharp
private bool SelectWeatherPlaceholder(ClimatePrefab prefab, out WeatherPrefab current, out WeatherPrefab next)
	{
		if (prefab.m_DefaultWeathers != null)
		{
			float num = float.MaxValue;
			int num2 = 0;
			for (int i = 0; i < prefab.m_DefaultWeathers.Length; i++)
			{
				WeatherPrefab weatherPrefab = prefab.m_DefaultWeathers[i];
				float num3 = math.max(weatherPrefab.m_CloudinessRange.x - (float)cloudiness, (float)cloudiness - weatherPrefab.m_CloudinessRange.y);
				if (num3 < num)
				{
					num2 = i;
					num = num3;
				}
			}
			current = prefab.m_DefaultWeathers[math.max(num2 - 1, 0)];
			next = prefab.m_DefaultWeathers[num2];
			return true;
		}
		current = null;
		next = null;
		return false;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_CurrentClimate = Entity.Null;
		m_CurrentWeatherEffects.ResizeUninitialized(0);
		m_NextWeatherEffects.ResizeUninitialized(0);
		m_TemperatureBaseHeight = 0f;
	}
```

- `private SortAndCheckUpdate(Unity.Collections.NativeList`1[[Game.Simulation.ClimateSystem+WeatherTempData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& weatherEffects, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& reference) : System.Boolean`  

```csharp
private bool SortAndCheckUpdate(ref NativeList<WeatherTempData> weatherEffects, ref NativeList<Entity> reference)
	{
		bool flag = false;
		weatherEffects.Sort();
		if (weatherEffects.Length != reference.Length)
		{
			flag = true;
			reference.ResizeUninitialized(weatherEffects.Length);
			for (int i = 0; i < weatherEffects.Length; i++)
			{
				reference[i] = weatherEffects[i].m_Entity;
			}
		}
		else
		{
			for (int j = 0; j < weatherEffects.Length; j++)
			{
				flag |= reference[j] != weatherEffects[j].m_Entity;
				reference[j] = weatherEffects[j].m_Entity;
			}
		}
		return flag;
	}
```

- `private UpdateSeason(Game.Prefabs.Climate.ClimatePrefab prefab, System.Single normalizedDate) : System.Void`  

```csharp
private void UpdateSeason(ClimatePrefab prefab, float normalizedDate)
	{
		SeasonInfo seasonInfo = m_CurrentSeason;
		float startRange;
		float endRange;
		(m_CurrentSeason, startRange, endRange) = prefab.FindSeasonByTime(normalizedDate);
		if (seasonInfo != m_CurrentSeason)
		{
			seasonTemperature = CalculateMeanTemperature(prefab, 48, startRange, endRange);
			seasonPrecipitation = CalculateMeanPrecipitation(prefab, 48, startRange, endRange);
			seasonCloudiness = CalculateMeanCloudiness(prefab, 48, startRange, endRange);
		}
	}
```

- `private UpdateWeather(Game.Prefabs.Climate.ClimatePrefab prefab) : System.Void`  

```csharp
private void UpdateWeather(ClimatePrefab prefab)
	{
		bool flag = false;
		NativeList<WeatherTempData> currentWeathers = new NativeList<WeatherTempData>(10, Allocator.Temp);
		NativeList<WeatherTempData> nextWeathers = new NativeList<WeatherTempData>(10, Allocator.Temp);
		if (SelectDefaultWeather(prefab, ref currentWeathers, ref nextWeathers))
		{
			if (SelectWeatherPlaceholder(prefab, out var current, out var next))
			{
				SelectRandomWeather(current, ref currentWeathers);
				SelectRandomWeather(next, ref nextWeathers);
				flag |= SortAndCheckUpdate(ref currentWeathers, ref m_CurrentWeatherEffects);
				flag |= SortAndCheckUpdate(ref nextWeathers, ref m_NextWeatherEffects);
			}
		}
		else
		{
			flag |= ResetWeatherEffects(ref m_CurrentWeatherEffects);
			flag |= ResetWeatherEffects(ref m_NextWeatherEffects);
		}
		currentWeathers.Dispose();
		nextWeathers.Dispose();
		if (flag)
		{
			ApplyWeatherEffects();
		}
	}
```


## Nested types

- `Game.Simulation.ClimateSystem+SeasonInfo`  
- `Game.Simulation.ClimateSystem+WeatherClassification`  
- `Game.Simulation.ClimateSystem+ClimateSample`  
- `Game.Simulation.ClimateSystem+WeatherTempData`  

