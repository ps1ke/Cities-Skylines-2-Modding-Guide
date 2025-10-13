# Game.UI.InGame.ClimateUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class ClimateUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Unity.Entities.EntityQuery m_ClimateQuery;
    private Unity.Entities.EntityQuery m_ClimateSeasonQuery;
    private Unity.Entities.EntityQuery m_SeasonChangedQuery;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TemperatureBinding;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.WeatherType> m_WeatherBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.String> m_SeasonBinding;
    private Unity.Entities.Entity m_CurrentSeason;
    public static const System.String kGroup;

    private System.Single m_TemperatureBindingValue { private get; }

    public ClimateUISystem();

    private System.Single <OnCreate>b__11_0();
    private static Game.UI.InGame.WeatherType FromWeatherClassification(Game.Simulation.ClimateSystem+WeatherClassification classification);
    private System.String GetCurrentSeasonNameID();
    public Game.UI.InGame.WeatherType GetWeather();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private static System.Void WriteWeatherType(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.WeatherType type);
}
```


## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Unity.Entities.EntityQuery m_ClimateQuery`  

```csharp
private Unity.Entities.EntityQuery m_ClimateQuery;
```

- `private Unity.Entities.EntityQuery m_ClimateSeasonQuery`  

```csharp
private Unity.Entities.EntityQuery m_ClimateSeasonQuery;
```

- `private Unity.Entities.EntityQuery m_SeasonChangedQuery`  

```csharp
private Unity.Entities.EntityQuery m_SeasonChangedQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TemperatureBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TemperatureBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.WeatherType> m_WeatherBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.WeatherType> m_WeatherBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_SeasonBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.String> m_SeasonBinding;
```

- `private Unity.Entities.Entity m_CurrentSeason`  

```csharp
private Unity.Entities.Entity m_CurrentSeason;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Properties

- `private System.Single m_TemperatureBindingValue { private get }`  

```csharp
private System.Single m_TemperatureBindingValue { private get; }
```


## Constructors

- `public ClimateUISystem()`  

```csharp
[Preserve]
	public ClimateUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__11_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__11_0();
```

- `private static FromWeatherClassification(Game.Simulation.ClimateSystem+WeatherClassification classification) : Game.UI.InGame.WeatherType`  

```csharp
private static WeatherType FromWeatherClassification(ClimateSystem.WeatherClassification classification)
	{
		return classification switch
		{
			ClimateSystem.WeatherClassification.Clear => WeatherType.Clear, 
			ClimateSystem.WeatherClassification.Few => WeatherType.Few, 
			ClimateSystem.WeatherClassification.Scattered => WeatherType.Scattered, 
			ClimateSystem.WeatherClassification.Broken => WeatherType.Broken, 
			ClimateSystem.WeatherClassification.Overcast => WeatherType.Overcast, 
			ClimateSystem.WeatherClassification.Stormy => WeatherType.Storm, 
			_ => WeatherType.Clear, 
		};
	}
```

- `private GetCurrentSeasonNameID() : System.String`  

```csharp
private string GetCurrentSeasonNameID()
	{
		return m_ClimateSystem.currentSeasonNameID;
	}
```

- `public GetWeather() : Game.UI.InGame.WeatherType`  

```csharp
public WeatherType GetWeather()
	{
		if (m_ClimateSystem.isPrecipitating)
		{
			if (m_ClimateSystem.isRaining)
			{
				return WeatherType.Rain;
			}
			if (m_ClimateSystem.isSnowing)
			{
				return WeatherType.Snow;
			}
			return WeatherType.Clear;
		}
		return FromWeatherClassification(m_ClimateSystem.classification);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		AddBinding(m_TemperatureBinding = new GetterValueBinding<float>("climate", "temperature", () => m_TemperatureBindingValue));
		AddBinding(m_WeatherBinding = new GetterValueBinding<WeatherType>("climate", "weather", GetWeather, new DelegateWriter<WeatherType>(WriteWeatherType)));
		AddBinding(m_SeasonBinding = new GetterValueBinding<string>("climate", "seasonNameId", GetCurrentSeasonNameID, ValueWriters.Nullable(new StringWriter())));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_TemperatureBinding.Update();
		m_WeatherBinding.Update();
		if (!m_SeasonBinding.Update() && m_CurrentSeason != m_ClimateSystem.currentSeason)
		{
			m_SeasonBinding.TriggerUpdate();
		}
		m_CurrentSeason = m_ClimateSystem.currentSeason;
	}
```

- `private static WriteWeatherType(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.WeatherType type) : System.Void`  

```csharp
private static void WriteWeatherType(IJsonWriter writer, WeatherType type)
	{
		writer.Write((int)type);
	}
```


