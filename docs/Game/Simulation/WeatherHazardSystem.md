# Game.Simulation.WeatherHazardSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WeatherHazardSystem : Game.GameSystemBase
{
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_PhenomenonQuery;
    private Game.Simulation.WeatherHazardSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATES_PER_DAY;

    public WeatherHazardSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_PhenomenonQuery`  

```csharp
private Unity.Entities.EntityQuery m_PhenomenonQuery;
```

- `private Game.Simulation.WeatherHazardSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WeatherHazardSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATES_PER_DAY`  

```csharp
private static const System.Int32 UPDATES_PER_DAY;
```


## Constructors

- `public WeatherHazardSystem()`  

```csharp
public WeatherHazardSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.WeatherHazardSystem+WeatherHazardJob`  
- `Game.Simulation.WeatherHazardSystem+TypeHandle`  

