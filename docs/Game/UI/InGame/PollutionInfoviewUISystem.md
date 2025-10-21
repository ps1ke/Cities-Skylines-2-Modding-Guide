# Game.UI.InGame.PollutionInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PollutionInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    protected Game.Simulation.CitySystem m_CitySystem;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageGroundPollution;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageWaterPollution;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageAirPollution;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageNoisePollution;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_374463591_0;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    protected System.Boolean Active { protected get; }

    public PollutionInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
}
```


## Fields

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `protected Game.Simulation.CitySystem m_CitySystem`  

```csharp
protected Game.Simulation.CitySystem m_CitySystem;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageGroundPollution`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageGroundPollution;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageWaterPollution`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageWaterPollution;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageAirPollution`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageAirPollution;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageNoisePollution`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageNoisePollution;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_374463591_0`  

```csharp
private Unity.Entities.EntityQuery __query_374463591_0;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public PollutionInfoviewUISystem()`  

```csharp
public PollutionInfoviewUISystem();
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

- `private ResetResults() : System.Void`  

```csharp
private System.Void ResetResults();
```


## Nested types

- `Game.UI.InGame.PollutionInfoviewUISystem+Result`  
- `Game.UI.InGame.PollutionInfoviewUISystem+CalculateAveragePollutionJob`  
- `Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle`  

