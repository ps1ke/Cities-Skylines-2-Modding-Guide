# Game.Simulation.ResourceAvailabilitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  
- `private Unity.Entities.EntityQuery m_WorkplaceGroup`  
- `private Unity.Entities.EntityQuery m_ServiceGroup`  
- `private Unity.Entities.EntityQuery m_RenterGroup`  
- `private Unity.Entities.EntityQuery m_ConvenienceFoodStoreGroup`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionGroup`  
- `private Unity.Entities.EntityQuery m_AttractionGroup`  
- `private Unity.Entities.EntityQuery m_ResourceSellerGroup`  
- `private Unity.Entities.EntityQuery m_TaxiQuery`  
- `private Unity.Entities.EntityQuery m_BusStopQuery`  
- `private Unity.Entities.EntityQuery m_TramSubwayQuery`  
- `private Unity.Entities.EntityQuery m_ParkingLaneQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Game.Net.AirwaySystem m_AirwaySystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  
- `private Unity.Entities.Entity m_AvailabilityContainer`  
- `private Game.Net.AvailableResource m_LastQueriedResource`  
- `private Game.Net.AvailableResource m_LastWrittenResource`  
- `private Game.Net.AvailableResource <appliedResource>k__BackingField`  
- `private Game.Simulation.ResourceAvailabilitySystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Properties

- `public Game.Net.AvailableResource appliedResource { get; private set }`  

## Constructors

- `public ResourceAvailabilitySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker, System.Single cost) : System.Void`  
- `private static AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker) : System.Void`  
- `private ApplyAvailability(Game.Net.AvailableResource resource, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle pathDeps) : Unity.Jobs.JobHandle`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private FindLocations(Game.Net.AvailableResource resource, Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> pathTargets, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private GetAvailabilityParameters(Game.Net.AvailableResource resource, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> datas) : Game.Pathfind.AvailabilityParameters`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.ResourceAvailabilitySystem+FindWorkplaceLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindAttractionLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindServiceLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindConsumerLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindConvenienceFoodStoreLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindOutsideConnectionLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindSellerLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindTaxiLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindBusStopLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindTramSubwayLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+ClearAvailabilityJob`  
- `Game.Simulation.ResourceAvailabilitySystem+ApplyAvailabilityJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindTaxiDistrictsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+ApplyTaxiAvailabilityJob`  
- `Game.Simulation.ResourceAvailabilitySystem+RefreshTaxiAvailabilityJob`  
- `Game.Simulation.ResourceAvailabilitySystem+TypeHandle`  

