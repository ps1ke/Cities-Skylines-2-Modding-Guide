# Game.Triggers.RadioTagSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class RadioTagSystem : Game.GameSystemBase
{
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_RecentTags;
    private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_InputQueue;
    private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_EmergencyInputQueue;
    private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_EmergencyQueue;
    private System.Collections.Generic.Dictionary<Game.Audio.Radio.Radio+SegmentType, System.Collections.Generic.List<Game.Triggers.RadioTag>> m_Events;
    private Unity.Jobs.JobHandle m_InputDependencies;
    private Unity.Jobs.JobHandle m_EmergencyInputDependencies;
    private Unity.Jobs.JobHandle m_EmergencyDependencies;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private static readonly System.Int32 kFrameDelay;
    private static readonly System.Int32 kMaxBufferSize;

    public RadioTagSystem();

    public System.Void AddEmergencyInputQueueWriter(Unity.Jobs.JobHandle handle);
    public System.Void AddInputQueueWriter(Unity.Jobs.JobHandle handle);
    private System.Void Clear();
    private System.Collections.Generic.List<Game.Triggers.RadioTag> EnsureList(Game.Audio.Radio.Radio+SegmentType segmentType);
    public System.Void FlushEvents(Game.Audio.Radio.Radio+SegmentType segmentType);
    public Unity.Collections.NativeQueue<Game.Triggers.RadioTag> GetEmergencyInputQueue(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeQueue<Game.Triggers.RadioTag> GetEmergencyQueue(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeQueue<Game.Triggers.RadioTag> GetInputQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    public System.Boolean TryPopEvent(Game.Audio.Radio.Radio+SegmentType segmentType, System.Boolean newestFirst, Game.Triggers.RadioTag& radioTag);
}
```


## Fields

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_RecentTags`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_RecentTags;
```

- `private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_InputQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_InputQueue;
```

- `private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_EmergencyInputQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_EmergencyInputQueue;
```

- `private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_EmergencyQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_EmergencyQueue;
```

- `private System.Collections.Generic.Dictionary<Game.Audio.Radio.Radio+SegmentType, System.Collections.Generic.List<Game.Triggers.RadioTag>> m_Events`  

```csharp
private System.Collections.Generic.Dictionary<Game.Audio.Radio.Radio+SegmentType, System.Collections.Generic.List<Game.Triggers.RadioTag>> m_Events;
```

- `private Unity.Jobs.JobHandle m_InputDependencies`  

```csharp
private Unity.Jobs.JobHandle m_InputDependencies;
```

- `private Unity.Jobs.JobHandle m_EmergencyInputDependencies`  

```csharp
private Unity.Jobs.JobHandle m_EmergencyInputDependencies;
```

- `private Unity.Jobs.JobHandle m_EmergencyDependencies`  

```csharp
private Unity.Jobs.JobHandle m_EmergencyDependencies;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private static readonly System.Int32 kFrameDelay`  

```csharp
private static readonly System.Int32 kFrameDelay;
```

- `private static readonly System.Int32 kMaxBufferSize`  

```csharp
private static readonly System.Int32 kMaxBufferSize;
```


## Constructors

- `public RadioTagSystem()`  

```csharp
public RadioTagSystem();
```


## Methods

- `public AddEmergencyInputQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddEmergencyInputQueueWriter(Unity.Jobs.JobHandle handle);
```

- `public AddInputQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddInputQueueWriter(Unity.Jobs.JobHandle handle);
```

- `private Clear() : System.Void`  

```csharp
private System.Void Clear();
```

- `private EnsureList(Game.Audio.Radio.Radio+SegmentType segmentType) : System.Collections.Generic.List<Game.Triggers.RadioTag>`  

```csharp
private System.Collections.Generic.List<Game.Triggers.RadioTag> EnsureList(Game.Audio.Radio.Radio+SegmentType segmentType);
```

- `public FlushEvents(Game.Audio.Radio.Radio+SegmentType segmentType) : System.Void`  

```csharp
public System.Void FlushEvents(Game.Audio.Radio.Radio+SegmentType segmentType);
```

- `public GetEmergencyInputQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  

```csharp
public Unity.Collections.NativeQueue<Game.Triggers.RadioTag> GetEmergencyInputQueue(Unity.Jobs.JobHandle& deps);
```

- `public GetEmergencyQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  

```csharp
public Unity.Collections.NativeQueue<Game.Triggers.RadioTag> GetEmergencyQueue(Unity.Jobs.JobHandle& deps);
```

- `public GetInputQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  

```csharp
public Unity.Collections.NativeQueue<Game.Triggers.RadioTag> GetInputQueue(Unity.Jobs.JobHandle& deps);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public TryPopEvent(Game.Audio.Radio.Radio+SegmentType segmentType, System.Boolean newestFirst, Game.Triggers.RadioTag& radioTag) : System.Boolean`  

```csharp
public System.Boolean TryPopEvent(Game.Audio.Radio.Radio+SegmentType segmentType, System.Boolean newestFirst, Game.Triggers.RadioTag& radioTag);
```


