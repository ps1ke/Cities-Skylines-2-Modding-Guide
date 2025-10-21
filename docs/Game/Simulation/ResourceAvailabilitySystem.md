# Game.Simulation.ResourceAvailabilitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceAvailabilitySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityQuery m_WorkplaceGroup;
    private Unity.Entities.EntityQuery m_ServiceGroup;
    private Unity.Entities.EntityQuery m_RenterGroup;
    private Unity.Entities.EntityQuery m_ConvenienceFoodStoreGroup;
    private Unity.Entities.EntityQuery m_OutsideConnectionGroup;
    private Unity.Entities.EntityQuery m_AttractionGroup;
    private Unity.Entities.EntityQuery m_ResourceSellerGroup;
    private Unity.Entities.EntityQuery m_TaxiQuery;
    private Unity.Entities.EntityQuery m_BusStopQuery;
    private Unity.Entities.EntityQuery m_TramSubwayQuery;
    private Unity.Entities.EntityQuery m_ParkingLaneQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private Unity.Entities.Entity m_AvailabilityContainer;
    private Game.Net.AvailableResource m_LastQueriedResource;
    private Game.Net.AvailableResource m_LastWrittenResource;
    private Game.Net.AvailableResource <appliedResource>k__BackingField;
    private Game.Simulation.ResourceAvailabilitySystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public Game.Net.AvailableResource appliedResource { get; private set; }

    public ResourceAvailabilitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker, System.Single cost);
    private static System.Void AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker);
    private Unity.Jobs.JobHandle ApplyAvailability(Game.Net.AvailableResource resource, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle pathDeps);
    public System.Void Deserialize<TReader>(TReader reader);
    private Unity.Jobs.JobHandle FindLocations(Game.Net.AvailableResource resource, Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> pathTargets, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Unity.Jobs.JobHandle inputDeps);
    private Game.Pathfind.AvailabilityParameters GetAvailabilityParameters(Game.Net.AvailableResource resource, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> datas);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Unity.Entities.EntityQuery m_WorkplaceGroup`  

```csharp
private Unity.Entities.EntityQuery m_WorkplaceGroup;
```

- `private Unity.Entities.EntityQuery m_ServiceGroup`  

```csharp
private Unity.Entities.EntityQuery m_ServiceGroup;
```

- `private Unity.Entities.EntityQuery m_RenterGroup`  

```csharp
private Unity.Entities.EntityQuery m_RenterGroup;
```

- `private Unity.Entities.EntityQuery m_ConvenienceFoodStoreGroup`  

```csharp
private Unity.Entities.EntityQuery m_ConvenienceFoodStoreGroup;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionGroup`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionGroup;
```

- `private Unity.Entities.EntityQuery m_AttractionGroup`  

```csharp
private Unity.Entities.EntityQuery m_AttractionGroup;
```

- `private Unity.Entities.EntityQuery m_ResourceSellerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ResourceSellerGroup;
```

- `private Unity.Entities.EntityQuery m_TaxiQuery`  

```csharp
private Unity.Entities.EntityQuery m_TaxiQuery;
```

- `private Unity.Entities.EntityQuery m_BusStopQuery`  

```csharp
private Unity.Entities.EntityQuery m_BusStopQuery;
```

- `private Unity.Entities.EntityQuery m_TramSubwayQuery`  

```csharp
private Unity.Entities.EntityQuery m_TramSubwayQuery;
```

- `private Unity.Entities.EntityQuery m_ParkingLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkingLaneQuery;
```

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

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private Unity.Entities.Entity m_AvailabilityContainer`  

```csharp
private Unity.Entities.Entity m_AvailabilityContainer;
```

- `private Game.Net.AvailableResource m_LastQueriedResource`  

```csharp
private Game.Net.AvailableResource m_LastQueriedResource;
```

- `private Game.Net.AvailableResource m_LastWrittenResource`  

```csharp
private Game.Net.AvailableResource m_LastWrittenResource;
```

- `private Game.Net.AvailableResource <appliedResource>k__BackingField`  

```csharp
private Game.Net.AvailableResource <appliedResource>k__BackingField;
```

- `private Game.Simulation.ResourceAvailabilitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResourceAvailabilitySystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Properties

- `public Game.Net.AvailableResource appliedResource { get; private set }`  

```csharp
public Game.Net.AvailableResource appliedResource { get; private set; }
```


## Constructors

- `public ResourceAvailabilitySystem()`  

```csharp
public ResourceAvailabilitySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker, System.Single cost) : System.Void`  

```csharp
private static System.Void AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker, System.Single cost);
```

- `private static AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker) : System.Void`  

```csharp
private static System.Void AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker);
```

- `private ApplyAvailability(Game.Net.AvailableResource resource, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle pathDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle ApplyAvailability(Game.Net.AvailableResource resource, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle pathDeps);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private FindLocations(Game.Net.AvailableResource resource, Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> pathTargets, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle FindLocations(Game.Net.AvailableResource resource, Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> pathTargets, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Unity.Jobs.JobHandle inputDeps);
```

- `private GetAvailabilityParameters(Game.Net.AvailableResource resource, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> datas) : Game.Pathfind.AvailabilityParameters`  

```csharp
private Game.Pathfind.AvailabilityParameters GetAvailabilityParameters(Game.Net.AvailableResource resource, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> datas);
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

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


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

