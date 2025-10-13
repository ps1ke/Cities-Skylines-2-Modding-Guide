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
[Preserve]
	public RadioTagSystem()
	{
	}
```


## Methods

- `public AddEmergencyInputQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddEmergencyInputQueueWriter(JobHandle handle)
	{
		m_EmergencyInputDependencies = JobHandle.CombineDependencies(m_EmergencyInputDependencies, handle);
	}
```

- `public AddInputQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddInputQueueWriter(JobHandle handle)
	{
		m_InputDependencies = JobHandle.CombineDependencies(m_InputDependencies, handle);
	}
```

- `private Clear() : System.Void`  

```csharp
private void Clear()
	{
		m_InputDependencies.Complete();
		m_EmergencyInputDependencies.Complete();
		m_EmergencyDependencies.Complete();
		m_InputQueue.Clear();
		m_EmergencyInputQueue.Clear();
		m_EmergencyQueue.Clear();
		m_RecentTags.Clear();
		m_Events.Clear();
	}
```

- `private EnsureList(Game.Audio.Radio.Radio+SegmentType segmentType) : System.Collections.Generic.List<Game.Triggers.RadioTag>`  

```csharp
private List<RadioTag> EnsureList(Radio.SegmentType segmentType)
	{
		if (!m_Events.ContainsKey(segmentType))
		{
			m_Events.Add(segmentType, new List<RadioTag>());
		}
		return m_Events[segmentType];
	}
```

- `public FlushEvents(Game.Audio.Radio.Radio+SegmentType segmentType) : System.Void`  

```csharp
public void FlushEvents(Radio.SegmentType segmentType)
	{
		EnsureList(segmentType).Clear();
	}
```

- `public GetEmergencyInputQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  

```csharp
public NativeQueue<RadioTag> GetEmergencyInputQueue(out JobHandle deps)
	{
		Assert.IsTrue(base.Enabled, "Can not write to queue when system isn't running");
		deps = m_EmergencyInputDependencies;
		return m_EmergencyInputQueue;
	}
```

- `public GetEmergencyQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  

```csharp
public NativeQueue<RadioTag> GetEmergencyQueue(out JobHandle deps)
	{
		Assert.IsTrue(base.Enabled, "Can not write to queue when system isn't running");
		deps = m_EmergencyDependencies;
		return m_EmergencyQueue;
	}
```

- `public GetInputQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  

```csharp
public NativeQueue<RadioTag> GetInputQueue(out JobHandle deps)
	{
		Assert.IsTrue(base.Enabled, "Can not write to queue when system isn't running");
		deps = m_InputDependencies;
		return m_InputQueue;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_InputQueue = new NativeQueue<RadioTag>(Allocator.Persistent);
		m_EmergencyInputQueue = new NativeQueue<RadioTag>(Allocator.Persistent);
		m_EmergencyQueue = new NativeQueue<RadioTag>(Allocator.Persistent);
		m_RecentTags = new NativeParallelHashMap<Entity, uint>(0, Allocator.Persistent);
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_Events = new Dictionary<Radio.SegmentType, List<RadioTag>>();
		base.Enabled = false;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_InputQueue.Dispose();
		m_EmergencyInputQueue.Dispose();
		m_EmergencyQueue.Dispose();
		m_RecentTags.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		Clear();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
		Clear();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_InputDependencies.Complete();
		m_EmergencyInputDependencies.Complete();
		m_EmergencyDependencies.Complete();
		RadioTag item;
		while (m_InputQueue.TryDequeue(out item))
		{
			List<RadioTag> list = EnsureList(item.m_SegmentType);
			if (!m_RecentTags.TryGetValue(item.m_Event, out var item2) || m_SimulationSystem.frameIndex >= item2 + kFrameDelay)
			{
				while (list.Contains(item))
				{
					list.Remove(item);
				}
				list.Add(item);
				list.RemoveRange(0, math.max(list.Count - kMaxBufferSize, 0));
				m_RecentTags[item.m_Event] = m_SimulationSystem.frameIndex;
			}
		}
		RadioTag item3;
		while (m_EmergencyInputQueue.TryDequeue(out item3))
		{
			if (!m_RecentTags.TryGetValue(item3.m_Event, out var item4) || m_SimulationSystem.frameIndex >= item4 + item3.m_EmergencyFrameDelay)
			{
				m_EmergencyQueue.Enqueue(item3);
				m_RecentTags[item3.m_Event] = m_SimulationSystem.frameIndex;
			}
		}
	}
```

- `public TryPopEvent(Game.Audio.Radio.Radio+SegmentType segmentType, System.Boolean newestFirst, Game.Triggers.RadioTag& radioTag) : System.Boolean`  

```csharp
public bool TryPopEvent(Radio.SegmentType segmentType, bool newestFirst, out RadioTag radioTag)
	{
		List<RadioTag> list = EnsureList(segmentType);
		if (list.Count > 0)
		{
			int index = (newestFirst ? (list.Count - 1) : 0);
			radioTag = list[index];
			list.RemoveAt(index);
			return true;
		}
		radioTag = default(RadioTag);
		return false;
	}
```


