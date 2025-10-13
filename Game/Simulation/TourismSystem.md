# Game.Simulation.TourismSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TourismSystem : Game.GameSystemBase
{
    private Unity.Mathematics.int2 m_CachedLodging;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Unity.Entities.EntityQuery m_AttractivenessProviderGroup;
    private Unity.Entities.EntityQuery m_HotelGroup;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.Simulation.TourismSystem+TypeHandle __TypeHandle;

    public TourismSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetRawTouristProbability(System.Int32 attractiveness);
    public static System.Single GetTouristProbability(Game.Prefabs.AttractivenessParameterData parameterData, System.Int32 attractiveness, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing);
    public static System.Int32 GetTouristRandomStay();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Single GetWeatherEffect(Game.Prefabs.AttractivenessParameterData parameterData, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Mathematics.int2 m_CachedLodging`  

```csharp
private Unity.Mathematics.int2 m_CachedLodging;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Unity.Entities.EntityQuery m_AttractivenessProviderGroup`  

```csharp
private Unity.Entities.EntityQuery m_AttractivenessProviderGroup;
```

- `private Unity.Entities.EntityQuery m_HotelGroup`  

```csharp
private Unity.Entities.EntityQuery m_HotelGroup;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.Simulation.TourismSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TourismSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TourismSystem()`  

```csharp
[Preserve]
	public TourismSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public static GetRawTouristProbability(System.Int32 attractiveness) : System.Single`  

```csharp
public static float GetRawTouristProbability(int attractiveness)
	{
		return (float)attractiveness / 1000f;
	}
```

- `public static GetTouristProbability(Game.Prefabs.AttractivenessParameterData parameterData, System.Int32 attractiveness, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing) : System.Single`  

```csharp
public static float GetTouristProbability(AttractivenessParameterData parameterData, int attractiveness, ClimateSystem.WeatherClassification weatherClassification, float temperature, float precipitation, bool isRaining, bool isSnowing)
	{
		return GetRawTouristProbability(attractiveness) * GetWeatherEffect(parameterData, weatherClassification, temperature, precipitation, isRaining, isSnowing);
	}
```

- `public static GetTouristRandomStay() : System.Int32`  

```csharp
public static int GetTouristRandomStay()
	{
		return 262144;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 32768;
	}
```

- `public static GetWeatherEffect(Game.Prefabs.AttractivenessParameterData parameterData, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing) : System.Single`  

```csharp
public static float GetWeatherEffect(AttractivenessParameterData parameterData, ClimateSystem.WeatherClassification weatherClassification, float temperature, float precipitation, bool isRaining, bool isSnowing)
	{
		float num = 1f;
		if (temperature > parameterData.m_AttractiveTemperature.x && temperature < parameterData.m_AttractiveTemperature.y)
		{
			num += Mathf.Lerp(parameterData.m_TemperatureAffect.x, 0f, math.abs(temperature - (parameterData.m_AttractiveTemperature.x + parameterData.m_AttractiveTemperature.y) / 2f) / ((parameterData.m_AttractiveTemperature.y - parameterData.m_AttractiveTemperature.x) / 2f));
		}
		else if (temperature > parameterData.m_ExtremeTemperature.y)
		{
			num += Mathf.Lerp(0f, parameterData.m_TemperatureAffect.y, (temperature - parameterData.m_ExtremeTemperature.y) / 10f);
		}
		else if (temperature < parameterData.m_ExtremeTemperature.x)
		{
			num += Mathf.Lerp(0f, parameterData.m_TemperatureAffect.y, (parameterData.m_ExtremeTemperature.x - temperature) / 10f);
		}
		if (isSnowing && precipitation > parameterData.m_SnowEffectRange.x && precipitation < parameterData.m_SnowEffectRange.y)
		{
			num += Mathf.Lerp(0f, parameterData.m_SnowRainExtremeAffect.x, (precipitation - parameterData.m_SnowEffectRange.x) / (parameterData.m_SnowEffectRange.y - parameterData.m_SnowEffectRange.x));
		}
		else if (isRaining && precipitation > parameterData.m_RainEffectRange.x && precipitation < parameterData.m_RainEffectRange.y)
		{
			num += Mathf.Lerp(0f, parameterData.m_SnowRainExtremeAffect.y, (precipitation - parameterData.m_RainEffectRange.x) / (parameterData.m_RainEffectRange.y - parameterData.m_RainEffectRange.x));
		}
		if (weatherClassification == ClimateSystem.WeatherClassification.Stormy)
		{
			num += parameterData.m_SnowRainExtremeAffect.z;
		}
		return math.clamp(num, 0.5f, 1.5f);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_CountHouseholdDataSystem = base.World.GetOrCreateSystemManaged<CountHouseholdDataSystem>();
		m_AttractivenessProviderGroup = GetEntityQuery(ComponentType.ReadWrite<AttractivenessProvider>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_HotelGroup = GetEntityQuery(ComponentType.ReadOnly<LodgingProvider>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ParameterQuery = GetEntityQuery(ComponentType.ReadOnly<AttractivenessParameterData>());
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		TourismJob jobData = new TourismJob
		{
			m_m_AttractivenessProviderChunks = m_AttractivenessProviderGroup.ToArchetypeChunkArray(Allocator.TempJob),
			m_HotelChunks = m_HotelGroup.ToArchetypeChunkArray(Allocator.TempJob),
			m_LodgingProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_LodgingProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_Tourisms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Tourism_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Parameters = m_ParameterQuery.GetSingleton<AttractivenessParameterData>(),
			m_ProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_AttractivenessProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_IsRaining = m_ClimateSystem.isRaining,
			m_IsSnowing = m_ClimateSystem.isSnowing,
			m_Temperature = m_ClimateSystem.temperature,
			m_Precipitation = m_ClimateSystem.precipitation,
			m_TouristCitizenCount = m_CountHouseholdDataSystem.TouristCitizenCount,
			m_WeatherClassification = m_ClimateSystem.classification
		};
		base.Dependency = IJobExtensions.Schedule(jobData, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.TourismSystem+TourismJob`  
- `Game.Simulation.TourismSystem+TypeHandle`  

