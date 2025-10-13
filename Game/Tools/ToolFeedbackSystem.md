# Game.Tools.ToolFeedbackSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolFeedbackSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private System.Collections.Generic.List<Unity.Entities.Entity> m_FeedbackContainers;
    private System.Collections.Generic.List<Unity.Entities.Entity> m_PendingContainers;
    private Unity.Collections.NativeParallelHashMap<Game.Tools.ToolFeedbackSystem+RecentKey, Game.Tools.ToolFeedbackSystem+RecentValue> m_RecentMap;
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Unity.Entities.EntityQuery m_AppliedQuery;
    private Unity.Entities.EntityQuery m_TargetQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Jobs.JobHandle m_RecentDeps;
    private Game.Tools.ToolFeedbackSystem+TypeHandle __TypeHandle;
    private static const System.Single INFINITE_RANGE;

    public ToolFeedbackSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void ProcessModifications();
    private System.Void UpdatePending();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private System.Collections.Generic.List<Unity.Entities.Entity> m_FeedbackContainers`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> m_FeedbackContainers;
```

- `private System.Collections.Generic.List<Unity.Entities.Entity> m_PendingContainers`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> m_PendingContainers;
```

- `private Unity.Collections.NativeParallelHashMap<Game.Tools.ToolFeedbackSystem+RecentKey, Game.Tools.ToolFeedbackSystem+RecentValue> m_RecentMap`  

```csharp
private Unity.Collections.NativeParallelHashMap<Game.Tools.ToolFeedbackSystem+RecentKey, Game.Tools.ToolFeedbackSystem+RecentValue> m_RecentMap;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_AppliedQuery`  

```csharp
private Unity.Entities.EntityQuery m_AppliedQuery;
```

- `private Unity.Entities.EntityQuery m_TargetQuery`  

```csharp
private Unity.Entities.EntityQuery m_TargetQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Jobs.JobHandle m_RecentDeps`  

```csharp
private Unity.Jobs.JobHandle m_RecentDeps;
```

- `private Game.Tools.ToolFeedbackSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ToolFeedbackSystem+TypeHandle __TypeHandle;
```

- `private static const System.Single INFINITE_RANGE`  

```csharp
private static const System.Single INFINITE_RANGE;
```


## Constructors

- `public ToolFeedbackSystem()`  

```csharp
public ToolFeedbackSystem();
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

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private ProcessModifications() : System.Void`  

```csharp
private System.Void ProcessModifications();
```

- `private UpdatePending() : System.Void`  

```csharp
private System.Void UpdatePending();
```


## Nested types

- `Game.Tools.ToolFeedbackSystem+RecentKey`  
- `Game.Tools.ToolFeedbackSystem+RecentValue`  
- `Game.Tools.ToolFeedbackSystem+RecentUpdate`  
- `Game.Tools.ToolFeedbackSystem+FeedbackType`  
- `Game.Tools.ToolFeedbackSystem+SetupCoverageSearchJob`  
- `Game.Tools.ToolFeedbackSystem+FillCoverageMapJob`  
- `Game.Tools.ToolFeedbackSystem+TargetCheckJob`  
- `Game.Tools.ToolFeedbackSystem+UpdateRecentMapJob`  
- `Game.Tools.ToolFeedbackSystem+TypeHandle`  

