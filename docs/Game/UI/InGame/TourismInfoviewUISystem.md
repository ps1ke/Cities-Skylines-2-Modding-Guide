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
public TourismInfoviewUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```

- `private UpdateAttractiveness() : System.Void`  

```csharp
private System.Void UpdateAttractiveness();
```

- `private UpdateAverageHotelPrice() : System.Void`  

```csharp
private System.Void UpdateAverageHotelPrice();
```

- `private UpdateTourismRate() : System.Void`  

```csharp
private System.Void UpdateTourismRate();
```

- `private UpdateWeatherEffect() : System.Void`  

```csharp
private System.Void UpdateWeatherEffect();
```


## Nested types

- `Game.UI.InGame.TourismInfoviewUISystem+Result`  
- `Game.UI.InGame.TourismInfoviewUISystem+CalculateAverageHotelPriceJob`  
- `Game.UI.InGame.TourismInfoviewUISystem+TypeHandle`  

