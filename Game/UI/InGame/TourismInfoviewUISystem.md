# Game.UI.InGame.TourismInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TourismInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_Attractiveness;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_TourismRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHotelPrice;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_WeatherEffect;
    private Unity.Entities.EntityQuery m_HotelQuery;
    private Unity.Entities.EntityQuery m_HotelModifiedQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.TourismInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1647950437_0;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public TourismInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateAttractiveness();
    private System.Void UpdateAverageHotelPrice();
    private System.Void UpdateTourismRate();
    private System.Void UpdateWeatherEffect();
}
```


## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_Attractiveness`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_Attractiveness;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_TourismRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_TourismRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHotelPrice`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHotelPrice;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_WeatherEffect`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_WeatherEffect;
```

- `private Unity.Entities.EntityQuery m_HotelQuery`  

```csharp
private Unity.Entities.EntityQuery m_HotelQuery;
```

- `private Unity.Entities.EntityQuery m_HotelModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_HotelModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.TourismInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.TourismInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1647950437_0`  

```csharp
private Unity.Entities.EntityQuery __query_1647950437_0;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public TourismInfoviewUISystem()`  

```csharp
[Preserve]
	public TourismInfoviewUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<AttractivenessParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1647950437_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		AddBinding(m_Attractiveness = new ValueBinding<IndicatorValue>("tourismInfo", "attractiveness", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		AddBinding(m_TourismRate = new ValueBinding<int>("tourismInfo", "tourismRate", 0));
		AddBinding(m_AverageHotelPrice = new ValueBinding<float>("tourismInfo", "averageHotelPrice", 0f));
		AddBinding(m_WeatherEffect = new ValueBinding<float>("tourismInfo", "weatherEffect", 0f));
		m_HotelQuery = GetEntityQuery(ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<LodgingProvider>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_HotelModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PropertyRenter>(),
				ComponentType.ReadOnly<LodgingProvider>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Created>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		RequireForUpdate<AttractivenessParameterData>();
		m_Results = new NativeArray<int>(2, Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		UpdateAttractiveness();
		UpdateTourismRate();
		UpdateWeatherEffect();
		UpdateAverageHotelPrice();
	}
```

- `private UpdateAttractiveness() : System.Void`  

```csharp
private void UpdateAttractiveness()
	{
		if (base.EntityManager.TryGetComponent<Tourism>(m_CitySystem.City, out var component))
		{
			m_Attractiveness.Update(new IndicatorValue(0f, 100f, component.m_Attractiveness));
		}
	}
```

- `private UpdateAverageHotelPrice() : System.Void`  

```csharp
private void UpdateAverageHotelPrice()
	{
		for (int i = 0; i < m_Results.Length; i++)
		{
			m_Results[i] = 0;
		}
		JobChunkExtensions.Schedule(new CalculateAverageHotelPriceJob
		{
			m_LodgingProviderHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_LodgingProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_HotelQuery, base.Dependency).Complete();
		int num = m_Results[1];
		float newValue = ((num > 0) ? (m_Results[0] / num) : 0);
		m_AverageHotelPrice.Update(newValue);
	}
```

- `private UpdateTourismRate() : System.Void`  

```csharp
private void UpdateTourismRate()
	{
		m_TourismRate.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.TouristCount));
	}
```

- `private UpdateWeatherEffect() : System.Void`  

```csharp
private void UpdateWeatherEffect()
	{
		m_WeatherEffect.Update(100f * (0f - (1f - TourismSystem.GetWeatherEffect(__query_1647950437_0.GetSingleton<AttractivenessParameterData>(), m_ClimateSystem.classification, m_ClimateSystem.temperature, m_ClimateSystem.precipitation, m_ClimateSystem.isRaining, m_ClimateSystem.isSnowing))));
	}
```


## Nested types

- `Game.UI.InGame.TourismInfoviewUISystem+Result`  
- `Game.UI.InGame.TourismInfoviewUISystem+CalculateAverageHotelPriceJob`  
- `Game.UI.InGame.TourismInfoviewUISystem+TypeHandle`  

