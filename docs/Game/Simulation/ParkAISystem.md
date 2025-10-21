# Game.Simulation.ParkAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkAISystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_ParkQuery;
    private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
    private Game.Simulation.ParkAISystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public ParkAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetMaintenancePriority(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData);
    public static Game.Buildings.ModifiedServiceCoverage GetModifiedServiceCoverage(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData, Game.Prefabs.CoverageData prefabCoverageData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_ParkQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkQuery;
```

- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
```

- `private Game.Simulation.ParkAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ParkAISystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public ParkAISystem()`  

```csharp
public ParkAISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetMaintenancePriority(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData) : System.Int32`  

```csharp
public static System.Int32 GetMaintenancePriority(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData);
```

- `public static GetModifiedServiceCoverage(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData, Game.Prefabs.CoverageData prefabCoverageData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : Game.Buildings.ModifiedServiceCoverage`  

```csharp
public static Game.Buildings.ModifiedServiceCoverage GetModifiedServiceCoverage(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData, Game.Prefabs.CoverageData prefabCoverageData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
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

- `Game.Simulation.ParkAISystem+ParkTickJob`  
- `Game.Simulation.ParkAISystem+TypeHandle`  

