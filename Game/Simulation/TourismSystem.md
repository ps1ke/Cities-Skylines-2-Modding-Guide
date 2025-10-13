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
public TourismSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetRawTouristProbability(System.Int32 attractiveness) : System.Single`  

```csharp
public static System.Single GetRawTouristProbability(System.Int32 attractiveness);
```

- `public static GetTouristProbability(Game.Prefabs.AttractivenessParameterData parameterData, System.Int32 attractiveness, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing) : System.Single`  

```csharp
public static System.Single GetTouristProbability(Game.Prefabs.AttractivenessParameterData parameterData, System.Int32 attractiveness, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing);
```

- `public static GetTouristRandomStay() : System.Int32`  

```csharp
public static System.Int32 GetTouristRandomStay();
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static GetWeatherEffect(Game.Prefabs.AttractivenessParameterData parameterData, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing) : System.Single`  

```csharp
public static System.Single GetWeatherEffect(Game.Prefabs.AttractivenessParameterData parameterData, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.TourismSystem+TourismJob`  
- `Game.Simulation.TourismSystem+TypeHandle`  

