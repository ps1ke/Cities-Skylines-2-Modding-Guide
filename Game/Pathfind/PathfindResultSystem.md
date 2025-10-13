# Game.Pathfind.PathfindResultSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathfindResultSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityCommandBuffer m_CommandBuffer;
    private Unity.Entities.EntityArchetype m_PathEventArchetype;
    private Unity.Entities.EntityArchetype m_CoverageEventArchetype;
    private System.UInt32 m_PendingSimulationFrameIndex;
    private System.Int32 m_PendingRequestCount;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> m_ResultListIndex;
    private System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> m_QueryStats;
    private Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_PathfindResultBuffer;
    private Unity.Collections.NativeList<Game.Pathfind.CoverageJobs+ResultItem> m_CoverageResultBuffer;
    private Unity.Collections.NativeList<Game.Pathfind.AvailabilityJobs+ResultItem> m_AvailabilityResultBuffer;
    private Game.Pathfind.PathfindResultSystem+TypeHandle __TypeHandle;

    public System.UInt32 pendingSimulationFrame { get; }
    public System.Int32 pendingRequestCount { get; }
    public System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> queryStats { get; }

    public PathfindResultSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddQueryStats(System.Object system, Game.Pathfind.PathfindResultSystem+QueryType queryType, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType, System.Int32 resultLength, System.Int32 graphTraversal);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
    private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
    private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
    private System.Void ProcessResults<T>(Game.Pathfind.PathfindQueueSystem+ActionList<T> list);
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityCommandBuffer m_CommandBuffer`  

```csharp
private Unity.Entities.EntityCommandBuffer m_CommandBuffer;
```

- `private Unity.Entities.EntityArchetype m_PathEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PathEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_CoverageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_CoverageEventArchetype;
```

- `private System.UInt32 m_PendingSimulationFrameIndex`  

```csharp
private System.UInt32 m_PendingSimulationFrameIndex;
```

- `private System.Int32 m_PendingRequestCount`  

```csharp
private System.Int32 m_PendingRequestCount;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> m_ResultListIndex`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> m_ResultListIndex;
```

- `private System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> m_QueryStats`  

```csharp
private System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> m_QueryStats;
```

- `private Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_PathfindResultBuffer`  

```csharp
private Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_PathfindResultBuffer;
```

- `private Unity.Collections.NativeList<Game.Pathfind.CoverageJobs+ResultItem> m_CoverageResultBuffer`  

```csharp
private Unity.Collections.NativeList<Game.Pathfind.CoverageJobs+ResultItem> m_CoverageResultBuffer;
```

- `private Unity.Collections.NativeList<Game.Pathfind.AvailabilityJobs+ResultItem> m_AvailabilityResultBuffer`  

```csharp
private Unity.Collections.NativeList<Game.Pathfind.AvailabilityJobs+ResultItem> m_AvailabilityResultBuffer;
```

- `private Game.Pathfind.PathfindResultSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.PathfindResultSystem+TypeHandle __TypeHandle;
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

- `public System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> queryStats { get }`  

```csharp
public System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> queryStats { get; }
```


## Constructors

- `public PathfindResultSystem()`  

```csharp
public PathfindResultSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AddQueryStats(System.Object system, Game.Pathfind.PathfindResultSystem+QueryType queryType, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType, System.Int32 resultLength, System.Int32 graphTraversal) : System.Void`  

```csharp
private System.Void AddQueryStats(System.Object system, Game.Pathfind.PathfindResultSystem+QueryType queryType, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType, System.Int32 resultLength, System.Int32 graphTraversal);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  

```csharp
private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
```

- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  

```csharp
private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
```

- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  

```csharp
private System.Void ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps);
```

- `private ProcessResults<T>(Game.Pathfind.PathfindQueueSystem+ActionList<T> list) : System.Void`  

```csharp
private System.Void ProcessResults<T>(Game.Pathfind.PathfindQueueSystem+ActionList<T> list);
```


## Nested types

- `Game.Pathfind.PathfindResultSystem+QueryType`  
- `Game.Pathfind.PathfindResultSystem+ResultKey`  
- `Game.Pathfind.PathfindResultSystem+ResultValue`  
- `Game.Pathfind.PathfindResultSystem+TypeHandle`  

