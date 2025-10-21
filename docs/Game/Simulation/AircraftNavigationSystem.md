# Game.Simulation.AircraftNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AircraftNavigationSystem : Game.GameSystemBase
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
    private Game.Simulation.AircraftNavigationSystem+TypeHandle __TypeHandle;

    public AircraftNavigationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  

```csharp
private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
```

- `private Game.Simulation.AircraftNavigationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AircraftNavigationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AircraftNavigationSystem()`  

```csharp
public AircraftNavigationSystem();
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

- `Game.Simulation.AircraftNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.AircraftNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.AircraftNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.AircraftNavigationSystem+TypeHandle`  

