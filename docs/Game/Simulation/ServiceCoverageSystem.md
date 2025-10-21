# Game.Simulation.ServiceCoverageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceCoverageSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private Unity.Collections.NativeQueue<Game.Simulation.ServiceCoverageSystem+QueueItem> m_PendingCoverages;
    private Game.Net.CoverageService m_LastCoverageService;
    private Game.Simulation.ServiceCoverageSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 COVERAGE_UPDATE_INTERVAL;

    public ServiceCoverageSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean EnqueuePendingCoverages(Unity.Jobs.JobHandle& outputDeps);
    private static Game.Net.CoverageService GetFrameService(System.UInt32 frame);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public static System.Void SetupPathfindMethods(Game.Net.CoverageService service, Game.Pathfind.PathfindParameters& pathfindParameters, Game.Pathfind.SetupQueueTarget& setupQueueTarget);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.ServiceCoverageSystem+QueueItem> m_PendingCoverages`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.ServiceCoverageSystem+QueueItem> m_PendingCoverages;
```

- `private Game.Net.CoverageService m_LastCoverageService`  

```csharp
private Game.Net.CoverageService m_LastCoverageService;
```

- `private Game.Simulation.ServiceCoverageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ServiceCoverageSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 COVERAGE_UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 COVERAGE_UPDATE_INTERVAL;
```


## Constructors

- `public ServiceCoverageSystem()`  

```csharp
public ServiceCoverageSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private EnqueuePendingCoverages(Unity.Jobs.JobHandle& outputDeps) : System.Boolean`  

```csharp
private System.Boolean EnqueuePendingCoverages(Unity.Jobs.JobHandle& outputDeps);
```

- `private static GetFrameService(System.UInt32 frame) : Game.Net.CoverageService`  

```csharp
private static Game.Net.CoverageService GetFrameService(System.UInt32 frame);
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public static SetupPathfindMethods(Game.Net.CoverageService service, Game.Pathfind.PathfindParameters& pathfindParameters, Game.Pathfind.SetupQueueTarget& setupQueueTarget) : System.Void`  

```csharp
public static System.Void SetupPathfindMethods(Game.Net.CoverageService service, Game.Pathfind.PathfindParameters& pathfindParameters, Game.Pathfind.SetupQueueTarget& setupQueueTarget);
```


## Nested types

- `Game.Simulation.ServiceCoverageSystem+ClearCoverageJob`  
- `Game.Simulation.ServiceCoverageSystem+CoverageElement`  
- `Game.Simulation.ServiceCoverageSystem+QueueItem`  
- `Game.Simulation.ServiceCoverageSystem+BuildingData`  
- `Game.Simulation.ServiceCoverageSystem+PrepareCoverageJob`  
- `Game.Simulation.ServiceCoverageSystem+ProcessCoverageJob`  
- `Game.Simulation.ServiceCoverageSystem+BuildingDataComparer`  
- `Game.Simulation.ServiceCoverageSystem+ApplyCoverageJob`  
- `Game.Simulation.ServiceCoverageSystem+SetupCoverageSearchJob`  
- `Game.Simulation.ServiceCoverageSystem+TypeHandle`  

