# Game.Simulation.CarNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CarNavigationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.CarNavigationSystem+Actions m_Actions;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Simulation.CarNavigationSystem+TypeHandle __TypeHandle;

    public CarNavigationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.CarNavigationSystem+Actions m_Actions`  

```csharp
private Game.Simulation.CarNavigationSystem+Actions m_Actions;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Simulation.CarNavigationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CarNavigationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CarNavigationSystem()`  

```csharp
public CarNavigationSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.CarNavigationSystem+Actions`  
- `Game.Simulation.CarNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.CarNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.CarNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.CarNavigationSystem+TrafficAmbienceEffect`  
- `Game.Simulation.CarNavigationSystem+ApplyTrafficAmbienceJob`  
- `Game.Simulation.CarNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.CarNavigationSystem+TypeHandle`  

