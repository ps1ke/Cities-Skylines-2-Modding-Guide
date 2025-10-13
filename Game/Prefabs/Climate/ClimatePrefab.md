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
public int CountElapsedSeasons(float startTime, float elapsedTime)
	{
		if (m_Seasons == null || m_Seasons.Length == 0)
		{
			return 0;
		}
		if (m_Seasons.Length == 1)
		{
			return 1;
		}
		int num = 0;
		for (int i = 0; i < m_SeasonsOrder.Length; i++)
		{
			ClimateSystem.SeasonInfo seasonInfo = m_Seasons[m_SeasonsOrder[i]];
			ClimateSystem.SeasonInfo obj = m_Seasons[m_SeasonsOrder[(i + 1) % m_Seasons.Length]];
			float startTime2 = seasonInfo.m_StartTime;
			float startTime3 = obj.m_StartTime;
			if (Intersect(startTime, elapsedTime, startTime2, startTime3))
			{
				num++;
			}
		}
		return num;
	}
```

- `public CreateSeasonAuroraCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonAuroraCurves`  

```csharp
public SeasonAuroraCurves CreateSeasonAuroraCurves()
	{
		SeasonAuroraCurves result = new SeasonAuroraCurves
		{
			amount = new AnimationCurve(),
			chance = new AnimationCurve()
		};
		for (int i = 0; i < m_Seasons.Length; i++)
		{
			var (seasonInfo, time) = GetSeasonAndMidTime(i);
			result.amount.AddKey(time, seasonInfo.m_AuroraAmount);
			result.chance.AddKey(time, seasonInfo.m_AuroraChance * 0.01f);
		}
		LoopCurve(result.amount, 0f, 10f);
		LoopCurve(result.chance);
		return result;
	}
```

- `public CreateSeasonPrecipCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonPrecipCurves`  

```csharp
public SeasonPrecipCurves CreateSeasonPrecipCurves()
	{
		SeasonPrecipCurves result = new SeasonPrecipCurves
		{
			cloudChance = new AnimationCurve(),
			cloudAmountMin = new AnimationCurve(),
			cloudAmountMax = new AnimationCurve(),
			precipChance = new AnimationCurve(),
			precipAmountMin = new AnimationCurve(),
			precipAmountMax = new AnimationCurve(),
			turbulence = new AnimationCurve()
		};
		for (int i = 0; i < m_Seasons.Length; i++)
		{
			(ClimateSystem.SeasonInfo, float) seasonAndMidTime = GetSeasonAndMidTime(i);
			ClimateSystem.SeasonInfo item = seasonAndMidTime.Item1;
			float item2 = seasonAndMidTime.Item2;
			float num = item.m_CloudAmount * 0.01f;
			float num2 = math.abs(item.m_CloudAmountDeviation) * 0.01f;
			float value = item.m_CloudChance * 0.01f;
			float num3 = item.m_PrecipitationAmount * 0.01f;
			float num4 = math.abs(item.m_PrecipitationAmountDeviation) * 0.01f;
			float value2 = item.m_PrecipitationChance * 0.01f;
			result.cloudAmountMin.AddKey(item2, num - num2);
			result.cloudAmountMax.AddKey(item2, num + num2);
			result.cloudChance.AddKey(item2, value);
			result.precipAmountMin.AddKey(item2, num3 - num4);
			result.precipAmountMax.AddKey(item2, num3 + num4);
			result.precipChance.AddKey(item2, value2);
			result.turbulence.AddKey(item2, item.m_Turbulence);
		}
		LoopCurve(result.cloudChance);
		LoopCurve(result.cloudAmountMin);
		LoopCurve(result.cloudAmountMax);
		LoopCurve(result.precipChance);
		LoopCurve(result.precipAmountMin);
		LoopCurve(result.precipAmountMax);
		LoopCurve(result.turbulence);
		return result;
	}
```

- `public CreateSeasonTemperatureCurves() : Game.Prefabs.Climate.ClimatePrefab+SeasonTempCurves`  

```csharp
public SeasonTempCurves CreateSeasonTemperatureCurves()
	{
		SeasonTempCurves result = new SeasonTempCurves
		{
			nightMin = new AnimationCurve(),
			nightMax = new AnimationCurve(),
			dayMin = new AnimationCurve(),
			dayMax = new AnimationCurve()
		};
		for (int i = 0; i < m_Seasons.Length; i++)
		{
			(ClimateSystem.SeasonInfo, float) seasonAndMidTime = GetSeasonAndMidTime(i);
			ClimateSystem.SeasonInfo item = seasonAndMidTime.Item1;
			float item2 = seasonAndMidTime.Item2;
			float2 tempNightDay = item.m_TempNightDay;
			float2 @float = math.abs(item.m_TempDeviationNightDay);
			result.nightMin.AddKey(item2, tempNightDay.x - @float.x);
			result.nightMax.AddKey(item2, tempNightDay.x + @float.x);
			result.dayMin.AddKey(item2, tempNightDay.y - @float.y);
			result.dayMax.AddKey(item2, tempNightDay.y + @float.y);
		}
		LoopCurve(result.nightMin, -100f, 100f);
		LoopCurve(result.nightMax, -100f, 100f);
		LoopCurve(result.dayMin, -100f, 100f);
		LoopCurve(result.dayMax, -100f, 100f);
		return result;
	}
```

- `internal EnsureSeasonsOrder(System.Boolean force = False) : System.Void`  

```csharp
internal void EnsureSeasonsOrder(bool force = false)
	{
		if (force || m_SeasonsOrder == null || m_SeasonsOrder.Length != m_Seasons.Length)
		{
			m_SeasonsOrder = (from v in Enumerable.Range(0, m_Seasons.Length)
				orderby m_Seasons[v].m_StartTime
				select v).ToArray();
		}
	}
```

- `public FindSeasonByTime(System.Single time) : System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single, System.Single>`  

```csharp
public System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single, System.Single> FindSeasonByTime(System.Single time);
```

- `private static GaussianRandom(System.Single mean, System.Single dev, Unity.Mathematics.Random& rng) : System.Single`  

```csharp
private static float GaussianRandom(float mean, float dev, ref Unity.Mathematics.Random rng)
	{
		int num = 0;
		float num4;
		do
		{
			float x = rng.NextFloat();
			float num2 = rng.NextFloat();
			float num3 = math.sqrt(-2f * math.log(x)) * math.sin(MathF.PI * 2f * num2);
			num4 = mean + dev * num3;
		}
		while (math.abs(num4 - mean) > 2f * dev && num++ < 20);
		return num4;
	}
```

- `private static GenCurveFromMinMax(System.Int32 keyCount, UnityEngine.AnimationCurve cmin, UnityEngine.AnimationCurve cmax, System.UInt32 seed, System.Single minValue, System.Single maxValue) : UnityEngine.AnimationCurve`  

```csharp
private static AnimationCurve GenCurveFromMinMax(int keyCount, AnimationCurve cmin, AnimationCurve cmax, uint seed, float minValue, float maxValue)
	{
		Unity.Mathematics.Random rng = new Unity.Mathematics.Random(seed);
		Keyframe[] array = new Keyframe[keyCount];
		for (int i = 0; i < array.Length; i++)
		{
			float time = (float)i / (float)array.Length * 12f;
			float num = cmin.Evaluate(time);
			float num2 = cmax.Evaluate(time);
			float dev = (num2 - num) / 2f * 0.78003126f;
			array[i].time = time;
			array[i].value = GaussianRandom((num + num2) / 2f, dev, ref rng);
		}
		AnimationCurve animationCurve = new AnimationCurve(array);
		LoopCurve(animationCurve, minValue, maxValue);
		return animationCurve;
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Seasons != null)
		{
			ClimateSystem.SeasonInfo[] seasons = m_Seasons;
			foreach (ClimateSystem.SeasonInfo seasonInfo in seasons)
			{
				prefabs.Add(seasonInfo.m_Prefab);
			}
		}
		if (m_DefaultWeather != null)
		{
			prefabs.Add(m_DefaultWeather);
		}
		if (m_DefaultWeathers == null)
		{
			return;
		}
		WeatherPrefab[] defaultWeathers = m_DefaultWeathers;
		foreach (WeatherPrefab weatherPrefab in defaultWeathers)
		{
			if (weatherPrefab.active)
			{
				prefabs.Add(weatherPrefab);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ClimateData>());
	}
```

- `public GetSeasonAndMidTime(System.Int32 index) : System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single>`  

```csharp
public System.ValueTuple<Game.Simulation.ClimateSystem+SeasonInfo, System.Single> GetSeasonAndMidTime(System.Int32 index);
```

- `private GetSeasonMidTime(System.Int32 index) : System.Single`  

```csharp
private float GetSeasonMidTime(int index)
	{
		ClimateSystem.SeasonInfo seasonInfo = m_Seasons[m_SeasonsOrder[index]];
		ClimateSystem.SeasonInfo obj = m_Seasons[m_SeasonsOrder[(index + 1) % m_Seasons.Length]];
		float startTime = seasonInfo.m_StartTime;
		float num = obj.m_StartTime;
		if (num < startTime)
		{
			num += 1f;
		}
		return (startTime + num) * 0.5f * 12f % 12f;
	}
```

- `private Intersect(System.Single startTime, System.Single elapsedTime, System.Single seasonStart, System.Single seasonEnd) : System.Boolean`  

```csharp
private bool Intersect(float startTime, float elapsedTime, float seasonStart, float seasonEnd)
	{
		if (seasonEnd < seasonStart)
		{
			if (startTime < seasonEnd)
			{
				startTime += 1f;
			}
			seasonEnd += 1f;
		}
		if (startTime > seasonEnd)
		{
			startTime -= 1f;
		}
		if (startTime < seasonEnd)
		{
			return startTime + elapsedTime > seasonStart;
		}
		return false;
	}
```

- `private static LoopCurve(UnityEngine.AnimationCurve curve, System.Single minValue = 0, System.Single maxValue = 1) : System.Void`  

```csharp
private static void LoopCurve(AnimationCurve curve, float minValue = 0f, float maxValue = 1f)
	{
		WrapMode preWrapMode = (curve.postWrapMode = WrapMode.Loop);
		curve.preWrapMode = preWrapMode;
		for (int i = 0; i < curve.length; i++)
		{
			curve.SmoothTangents(i, 1f / 3f);
		}
		Keyframe[] keys = curve.keys;
		bool flag = false;
		for (int j = 0; j < keys.Length; j++)
		{
			Keyframe keyframe = keys[j];
			if (keyframe.value <= minValue)
			{
				keyframe.value = minValue;
				float inTangent = (keyframe.outTangent = 0f);
				keyframe.inTangent = inTangent;
				keys[j] = keyframe;
				flag = true;
			}
			if (keyframe.value >= maxValue)
			{
				keyframe.value = maxValue;
				float inTangent = (keyframe.outTangent = 0f);
				keyframe.inTangent = inTangent;
				keys[j] = keyframe;
				flag = true;
			}
		}
		if (flag)
		{
			curve.keys = keys;
		}
		Keyframe key = keys[0];
		key.inTangent = 0f;
		key.outTangent = 0f;
		curve.MoveKey(0, key);
		key.time += 12f;
		curve.AddKey(key);
	}
```

- `private RebuildAuroraCurves(System.UInt32 seed) : System.Void`  

```csharp
private void RebuildAuroraCurves(uint seed)
	{
		SeasonAuroraCurves seasonAuroraCurves = CreateSeasonAuroraCurves();
		Unity.Mathematics.Random random = new Unity.Mathematics.Random(seed + 5000);
		Keyframe[] array = new Keyframe[288];
		float num = random.NextFloat(0f, 100f);
		float y = random.NextFloat(0f, 100f);
		for (int i = 0; i < array.Length; i++)
		{
			float num2 = (float)i / (float)array.Length * 12f;
			array[i].time = num2;
			float num3 = math.max(0f, seasonAuroraCurves.amount.Evaluate(num2));
			float num4 = 0.1f;
			float num5 = SmoothNoise(num2 * 4f, y);
			num5 *= num4;
			num5 *= num3;
			num3 = math.max(0f, num3 + num5);
			float num6 = math.saturate(seasonAuroraCurves.chance.Evaluate(num2));
			float num7 = math.saturate((SmoothNoise(num2, num) + SmoothNoise(num2 * 2f, num + 7f) * 0.5f) * 0.5f + 0.5f);
			if (num7 > num6)
			{
				num3 *= 1f - math.saturate((num7 - num6) * 8f);
			}
			array[i].value = num3;
		}
		m_Aurora = new AnimationCurve(array);
		LoopCurve(m_Aurora, 0f, 10f);
	}
```

- `public RebuildCurves() : System.Void`  

```csharp
public void RebuildCurves()
	{
		EnsureSeasonsOrder(force: true);
		uint num = (uint)m_RandomSeed;
		if (num == 0)
		{
			num = (uint)(Time.realtimeSinceStartup * 10f);
		}
		RebuildTemperatureCurves(num);
		RebuildPrecipitationCurves(num);
		RebuildAuroraCurves(num);
		RebuildFogCurves(num);
	}
```

- `private RebuildFogCurves(System.UInt32 seed) : System.Void`  

```csharp
private void RebuildFogCurves(uint seed)
	{
		Keyframe[] array = new Keyframe[288];
		float num = 1f / 24f;
		float num2 = 2f;
		float num3 = 0.15f;
		float num4 = -1f;
		float num5 = 25f;
		float num6 = 0.5f;
		for (int i = 0; i < array.Length; i++)
		{
			float num7 = (float)i / (float)array.Length * 12f;
			array[i].time = num7;
			float num8 = m_Cloudiness.Evaluate(num7);
			float num9 = m_Precipitation.Evaluate(num7);
			float num10 = m_Temperature.Evaluate(num7);
			float num11 = 0f;
			if (num8 > num3 && num10 > num4 && num10 < num5 && num9 < num6)
			{
				float num12 = m_Temperature.Evaluate(num7 - 8f * num);
				float num13 = m_Temperature.Evaluate(num7 - 7f * num);
				float num14 = m_Temperature.Evaluate(num7 - 6f * num);
				float num15 = m_Temperature.Evaluate(num7 - 5f * num);
				float num16 = m_Temperature.Evaluate(num7 - 4f * num);
				float num17 = m_Temperature.Evaluate(num7 - 3f * num);
				float num18 = m_Temperature.Evaluate(num7 - 2f * num);
				float num19 = m_Temperature.Evaluate(num7 - 1f * num);
				if (num12 - num13 > num2)
				{
					num11 += 0.19f;
				}
				if (num13 - num14 > num2)
				{
					num11 += 0.17f;
				}
				if (num14 - num15 > num2)
				{
					num11 += 0.12f;
				}
				if (num15 - num16 > num2)
				{
					num11 += 0.09f;
				}
				if (num16 - num17 > num2)
				{
					num11 += 0.11f;
				}
				if (num17 - num18 > num2)
				{
					num11 += 0.13f;
				}
				if (num18 - num19 > num2)
				{
					num11 += 0.14f;
				}
				if (num19 - num10 > num2)
				{
					num11 += 0.15f;
				}
				if (num12 - num15 > num2)
				{
					num11 += 0.21f;
				}
				if (num13 - num16 > num2)
				{
					num11 += 0.18f;
				}
				if (num14 - num17 > num2)
				{
					num11 += 0.07f;
				}
			}
			array[i].value = math.saturate(num11);
		}
		m_Fog = new AnimationCurve(array);
		LoopCurve(m_Aurora);
	}
```

- `private RebuildPrecipitationCurves(System.UInt32 seed) : System.Void`  

```csharp
private void RebuildPrecipitationCurves(uint seed)
	{
		SeasonPrecipCurves seasonPrecipCurves = CreateSeasonPrecipCurves();
		AnimationCurve animationCurve = GenCurveFromMinMax(12, seasonPrecipCurves.cloudAmountMin, seasonPrecipCurves.cloudAmountMax, seed + 1000, 0f, 1f);
		Unity.Mathematics.Random random = new Unity.Mathematics.Random(seed + 2000);
		Keyframe[] array = new Keyframe[1728];
		float num = random.NextFloat(0f, 100f);
		float y = random.NextFloat(0f, 100f);
		for (int i = 0; i < array.Length; i++)
		{
			float num2 = (float)i / (float)array.Length * 12f;
			array[i].time = num2;
			float num3 = math.saturate(animationCurve.Evaluate(num2));
			float num4 = math.saturate(seasonPrecipCurves.turbulence.Evaluate(num2));
			float num5 = SmoothNoise(num2 * 4f, y);
			num5 *= num4;
			num5 *= num3;
			num3 = math.saturate(num3 + num5);
			float num6 = math.saturate(seasonPrecipCurves.cloudChance.Evaluate(num2));
			float num7 = math.saturate((SmoothNoise(num2, num) + SmoothNoise(num2 * 2f, num + 7f) * 0.5f) * 0.5f + 0.5f);
			if (num7 > num6)
			{
				num3 *= 1f - math.saturate((num7 - num6) * 2f);
			}
			array[i].value = num3;
		}
		m_Cloudiness = new AnimationCurve(array);
		LoopCurve(m_Cloudiness);
		AnimationCurve animationCurve2 = GenCurveFromMinMax(12, seasonPrecipCurves.precipAmountMin, seasonPrecipCurves.precipAmountMax, seed + 3000, 0f, 1f);
		random = new Unity.Mathematics.Random(seed + 4000);
		array = new Keyframe[1728];
		num = random.NextFloat(0f, 100f);
		y = random.NextFloat(0f, 100f);
		for (int j = 0; j < array.Length; j++)
		{
			float num8 = (float)j / (float)array.Length * 12f;
			array[j].time = num8;
			float num9 = math.saturate(animationCurve2.Evaluate(num8));
			float num10 = math.saturate(seasonPrecipCurves.turbulence.Evaluate(num8));
			float num11 = SmoothNoise(num8 * 4f, y);
			num11 *= num10;
			num11 *= num9;
			num9 = math.saturate(num9 + num11);
			float num12 = math.saturate(seasonPrecipCurves.precipChance.Evaluate(num8));
			float num13 = math.saturate((SmoothNoise(num8, num) + SmoothNoise(num8 * 2f, num + 7f) * 0.5f) * 0.5f + 0.5f);
			if (num13 > num12)
			{
				num9 *= 1f - math.saturate((num13 - num12) * 2f);
			}
			float num14 = m_Cloudiness.Evaluate(num8);
			if (num14 < 0.7f)
			{
				num9 *= num14 / 0.7f;
			}
			if (num14 < 0.4f)
			{
				num9 *= num14 / 0.4f;
			}
			if (num14 < 0.2f)
			{
				num9 = 0f;
			}
			array[j].value = num9;
		}
		m_Precipitation = new AnimationCurve(array);
		LoopCurve(m_Precipitation);
	}
```

- `private RebuildTemperatureCurves(System.UInt32 seed) : System.Void`  

```csharp
private void RebuildTemperatureCurves(uint seed)
	{
		SeasonTempCurves seasonTempCurves = CreateSeasonTemperatureCurves();
		AnimationCurve animationCurve = GenCurveFromMinMax(12, seasonTempCurves.nightMin, seasonTempCurves.nightMax, seed + 10000, -100f, 100f);
		AnimationCurve animationCurve2 = GenCurveFromMinMax(12, seasonTempCurves.dayMin, seasonTempCurves.dayMax, seed + 11000, -100f, 100f);
		Keyframe[] array = new Keyframe[288];
		for (int i = 0; i < 288; i++)
		{
			float num = (float)i / 288f * 12f;
			array[i].time = num;
			float start = animationCurve.Evaluate(num);
			float end = animationCurve2.Evaluate(num);
			float num2 = (float)(i % 24) / 24f;
			float num3 = noise.cnoise(new float2(num * 4f, 0f)) / 24f * 4f;
			float t = (0f - math.cos((num2 + num3) * MathF.PI * 2f)) * 0.5f + 0.5f;
			array[i].value = math.lerp(start, end, t);
		}
		m_Temperature = new AnimationCurve(array);
		LoopCurve(m_Temperature, -100f, 100f);
	}
```

- `private static SmoothNoise(System.Single x, System.Single y = 0) : System.Single`  

```csharp
private static float SmoothNoise(float x, float y = 0f)
	{
		return noise.snoise(new float2(x, y));
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().Name);
		writer.PropertyName("latitude");
		writer.Write(m_Latitude);
		writer.PropertyName("longitude");
		writer.Write(m_Longitude);
		writer.PropertyName("freezingTemperature");
		writer.Write(m_FreezingTemperature);
		writer.PropertyName("seasons");
		writer.Write((IList<ClimateSystem.SeasonInfo>)m_Seasons);
		writer.TypeEnd();
	}
```


## Nested types

- `Game.Prefabs.Climate.ClimatePrefab+SeasonTempCurves`  
- `Game.Prefabs.Climate.ClimatePrefab+SeasonPrecipCurves`  
- `Game.Prefabs.Climate.ClimatePrefab+SeasonAuroraCurves`  

