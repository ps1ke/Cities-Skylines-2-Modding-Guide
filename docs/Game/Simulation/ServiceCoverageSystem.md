# Game.Simulation.ServiceCoverageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Game.Net.AirwaySystem m_AirwaySystem`  
- `private Unity.Entities.EntityQuery m_EdgeQuery`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  
- `private Unity.Collections.NativeQueue<Game.Simulation.ServiceCoverageSystem+QueueItem> m_PendingCoverages`  
- `private Game.Net.CoverageService m_LastCoverageService`  
- `private Game.Simulation.ServiceCoverageSystem+TypeHandle __TypeHandle`  
- `public static const System.UInt32 COVERAGE_UPDATE_INTERVAL`  

## Constructors

- `public ServiceCoverageSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private EnqueuePendingCoverages(Unity.Jobs.JobHandle& outputDeps) : System.Boolean`  
- `private static GetFrameService(System.UInt32 frame) : Game.Net.CoverageService`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static SetupPathfindMethods(Game.Net.CoverageService service, Game.Pathfind.PathfindParameters& pathfindParameters, Game.Pathfind.SetupQueueTarget& setupQueueTarget) : System.Void`  

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

