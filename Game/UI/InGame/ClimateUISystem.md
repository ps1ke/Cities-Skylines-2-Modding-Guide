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
public ClimateUISystem();
```


## Methods

- `private <OnCreate>b__11_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__11_0();
```

- `private static FromWeatherClassification(Game.Simulation.ClimateSystem+WeatherClassification classification) : Game.UI.InGame.WeatherType`  

```csharp
private static Game.UI.InGame.WeatherType FromWeatherClassification(Game.Simulation.ClimateSystem+WeatherClassification classification);
```

- `private GetCurrentSeasonNameID() : System.String`  

```csharp
private System.String GetCurrentSeasonNameID();
```

- `public GetWeather() : Game.UI.InGame.WeatherType`  

```csharp
public Game.UI.InGame.WeatherType GetWeather();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private static WriteWeatherType(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.WeatherType type) : System.Void`  

```csharp
private static System.Void WriteWeatherType(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.WeatherType type);
```


