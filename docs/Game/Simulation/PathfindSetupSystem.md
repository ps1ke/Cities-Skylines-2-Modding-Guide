# Game.Simulation.PathfindSetupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathfindSetupSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private Game.Simulation.CommonPathfindSetup m_CommonPathfindSetup;
    private Game.Simulation.PostServicePathfindSetup m_PostServicePathfindSetup;
    private Game.Simulation.GarbagePathfindSetup m_GarbagePathfindSetup;
    private Game.Simulation.TransportPathfindSetup m_TransportPathfindSetup;
    private Game.Simulation.PolicePathfindSetup m_PolicePathfindSetup;
    private Game.Simulation.FirePathfindSetup m_FirePathfindSetup;
    private Game.Simulation.HealthcarePathfindSetup m_HealthcarePathfindSetup;
    private Game.Simulation.AreaPathfindSetup m_AreaPathfindSetup;
    private Game.Simulation.RoadPathfindSetup m_RoadPathfindSetup;
    private Game.Simulation.CitizenPathfindSetup m_CitizenPathfindSetup;
    private Game.Simulation.ResourcePathfindSetup m_ResourcePathfindSetup;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupList;
    private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_ActiveQueues;
    private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_FreeQueues;
    private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+ActionListItem> m_ActionList;
    private Unity.Jobs.JobHandle m_QueueDependencies;
    private Unity.Jobs.JobHandle m_SetupDependencies;
    private System.UInt32 m_QueueSimulationFrameIndex;
    private System.UInt32 m_SetupSimulationFrameIndex;
    private System.Int32 m_PendingRequestCount;

    public System.UInt32 pendingSimulationFrame { get; }
    public System.Int32 pendingRequestCount { get; }

    public PathfindSetupSystem();

    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public System.Void CompleteSetup();
    private System.Void FindTargets(System.Int32 startIndex, System.Int32 endIndex);
    private Unity.Jobs.JobHandle FindTargets(Game.Pathfind.SetupTargetType targetType, Game.Simulation.PathfindSetupSystem+SetupData& setupData);
    public Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> GetQueue(System.Object system, System.Int32 maxDelayFrames, System.Int32 spreadFrames);
    public Unity.Entities.EntityQuery GetSetupQuery(Unity.Entities.EntityQueryDesc[] entityQueryDesc);
    public Unity.Entities.EntityQuery GetSetupQuery(Unity.Entities.ComponentType[] componentTypes);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private Game.Simulation.CommonPathfindSetup m_CommonPathfindSetup`  

```csharp
private Game.Simulation.CommonPathfindSetup m_CommonPathfindSetup;
```

- `private Game.Simulation.PostServicePathfindSetup m_PostServicePathfindSetup`  

```csharp
private Game.Simulation.PostServicePathfindSetup m_PostServicePathfindSetup;
```

- `private Game.Simulation.GarbagePathfindSetup m_GarbagePathfindSetup`  

```csharp
private Game.Simulation.GarbagePathfindSetup m_GarbagePathfindSetup;
```

- `private Game.Simulation.TransportPathfindSetup m_TransportPathfindSetup`  

```csharp
private Game.Simulation.TransportPathfindSetup m_TransportPathfindSetup;
```

- `private Game.Simulation.PolicePathfindSetup m_PolicePathfindSetup`  

```csharp
private Game.Simulation.PolicePathfindSetup m_PolicePathfindSetup;
```

- `private Game.Simulation.FirePathfindSetup m_FirePathfindSetup`  

```csharp
private Game.Simulation.FirePathfindSetup m_FirePathfindSetup;
```

- `private Game.Simulation.HealthcarePathfindSetup m_HealthcarePathfindSetup`  

```csharp
private Game.Simulation.HealthcarePathfindSetup m_HealthcarePathfindSetup;
```

- `private Game.Simulation.AreaPathfindSetup m_AreaPathfindSetup`  

```csharp
private Game.Simulation.AreaPathfindSetup m_AreaPathfindSetup;
```

- `private Game.Simulation.RoadPathfindSetup m_RoadPathfindSetup`  

```csharp
private Game.Simulation.RoadPathfindSetup m_RoadPathfindSetup;
```

- `private Game.Simulation.CitizenPathfindSetup m_CitizenPathfindSetup`  

```csharp
private Game.Simulation.CitizenPathfindSetup m_CitizenPathfindSetup;
```

- `private Game.Simulation.ResourcePathfindSetup m_ResourcePathfindSetup`  

```csharp
private Game.Simulation.ResourcePathfindSetup m_ResourcePathfindSetup;
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

- `private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupList`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupList;
```

- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_ActiveQueues`  

```csharp
private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_ActiveQueues;
```

- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_FreeQueues`  

```csharp
private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_FreeQueues;
```

- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+ActionListItem> m_ActionList`  

```csharp
private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+ActionListItem> m_ActionList;
```

- `private Unity.Jobs.JobHandle m_QueueDependencies`  

```csharp
private Unity.Jobs.JobHandle m_QueueDependencies;
```

- `private Unity.Jobs.JobHandle m_SetupDependencies`  

```csharp
private Unity.Jobs.JobHandle m_SetupDependencies;
```

- `private System.UInt32 m_QueueSimulationFrameIndex`  

```csharp
private System.UInt32 m_QueueSimulationFrameIndex;
```

- `private System.UInt32 m_SetupSimulationFrameIndex`  

```csharp
private System.UInt32 m_SetupSimulationFrameIndex;
```

- `private System.Int32 m_PendingRequestCount`  

```csharp
private System.Int32 m_PendingRequestCount;
```


## Properties

- `public System.UInt32 pendingSimulationFrame { get }`  

```csharp
public System.UInt32 pendingSimulationFrame { get; }
```

- `public System.Int32 pendingRequestCount { get }`  

```csharp
public System.Int32 pendingRequestCount { get; }
```


## Constructors

- `public PathfindSetupSystem()`  

```csharp
public PathfindSetupSystem();
```


## Methods

- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
```

- `public CompleteSetup() : System.Void`  

```csharp
public System.Void CompleteSetup();
```

- `private FindTargets(System.Int32 startIndex, System.Int32 endIndex) : System.Void`  

```csharp
private System.Void FindTargets(System.Int32 startIndex, System.Int32 endIndex);
```

- `private FindTargets(Game.Pathfind.SetupTargetType targetType, Game.Simulation.PathfindSetupSystem+SetupData& setupData) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle FindTargets(Game.Pathfind.SetupTargetType targetType, Game.Simulation.PathfindSetupSystem+SetupData& setupData);
```

- `public GetQueue(System.Object system, System.Int32 maxDelayFrames, System.Int32 spreadFrames = 0) : Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem>`  

```csharp
public Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> GetQueue(System.Object system, System.Int32 maxDelayFrames, System.Int32 spreadFrames);
```

- `public GetSetupQuery(Unity.Entities.EntityQueryDesc[] entityQueryDesc) : Unity.Entities.EntityQuery`  

```csharp
public Unity.Entities.EntityQuery GetSetupQuery(Unity.Entities.EntityQueryDesc[] entityQueryDesc);
```

- `public GetSetupQuery(Unity.Entities.ComponentType[] componentTypes) : Unity.Entities.EntityQuery`  

```csharp
public Unity.Entities.EntityQuery GetSetupQuery(Unity.Entities.ComponentType[] componentTypes);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.PathfindSetupSystem+SetupData`  
- `Game.Simulation.PathfindSetupSystem+SetupListItem`  
- `Game.Simulation.PathfindSetupSystem+ActionListItem`  
- `Game.Simulation.PathfindSetupSystem+SetupQueue`  
- `Game.Simulation.PathfindSetupSystem+DequePathTargetsJob`  

