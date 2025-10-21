# Game.Simulation.BuildingConstructionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingConstructionSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.ZoneSpawnSystem m_ZoneSpawnSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Game.Simulation.BuildingConstructionSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATE_INTERVAL_BITS;
    public static const System.UInt32 UPDATE_INTERVAL;

    public BuildingConstructionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Simulation.ZoneSpawnSystem m_ZoneSpawnSystem`  

```csharp
private Game.Simulation.ZoneSpawnSystem m_ZoneSpawnSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Game.Simulation.BuildingConstructionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BuildingConstructionSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATE_INTERVAL_BITS`  

```csharp
private static const System.Int32 UPDATE_INTERVAL_BITS;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public BuildingConstructionSystem()`  

```csharp
public BuildingConstructionSystem();
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

- `Game.Simulation.BuildingConstructionSystem+BuildingConstructionJob`  
- `Game.Simulation.BuildingConstructionSystem+TypeHandle`  

