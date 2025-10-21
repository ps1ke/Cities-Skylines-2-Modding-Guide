# Game.Simulation.WeatherPhenomenonSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WeatherPhenomenonSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_PhenomenonQuery;
    private Unity.Entities.EntityArchetype m_FaceWeatherArchetype;
    private Unity.Entities.EntityArchetype m_ImpactArchetype;
    private Unity.Entities.EntityArchetype m_EndangerArchetype;
    private Unity.Entities.EntityArchetype m_EventIgniteArchetype;
    private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
    private Game.Simulation.WeatherPhenomenonSystem+TypeHandle __TypeHandle;

    public WeatherPhenomenonSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem`  

```csharp
private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_PhenomenonQuery`  

```csharp
private Unity.Entities.EntityQuery m_PhenomenonQuery;
```

- `private Unity.Entities.EntityArchetype m_FaceWeatherArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_FaceWeatherArchetype;
```

- `private Unity.Entities.EntityArchetype m_ImpactArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ImpactArchetype;
```

- `private Unity.Entities.EntityArchetype m_EndangerArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EndangerArchetype;
```

- `private Unity.Entities.EntityArchetype m_EventIgniteArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventIgniteArchetype;
```

- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
```

- `private Game.Simulation.WeatherPhenomenonSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WeatherPhenomenonSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WeatherPhenomenonSystem()`  

```csharp
public WeatherPhenomenonSystem();
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

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.WeatherPhenomenonSystem+WeatherPhenomenonJob`  
- `Game.Simulation.WeatherPhenomenonSystem+TypeHandle`  

