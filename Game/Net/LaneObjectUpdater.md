# Game.Net.LaneObjectUpdater

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LaneObjectUpdater
{
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
    private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue;
    private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue;

    public LaneObjectUpdater(Unity.Entities.SystemBase system);

    public Unity.Jobs.JobHandle Apply(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle dependencies);
    public Game.Net.LaneObjectCommandBuffer Begin(Unity.Collections.Allocator allocator);
}
```


## Fields

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  

```csharp
private Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
```

- `private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue`  

```csharp
private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue;
```

- `private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue;
```


## Constructors

- `public LaneObjectUpdater(Unity.Entities.SystemBase system)`  

```csharp
public LaneObjectUpdater(SystemBase system)
	{
		m_SearchSystem = system.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_LaneObjects = system.GetBufferLookup<LaneObject>();
		m_LaneActionQueue = default(NativeParallelQueue<LaneObjectAction>);
		m_TreeActionQueue = default(NativeQueue<TreeObjectAction>);
	}
```


## Methods

- `public Apply(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle dependencies) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle Apply(SystemBase system, JobHandle dependencies)
	{
		m_LaneObjects.Update(system);
		UpdateLaneObjectsJob jobData = new UpdateLaneObjectsJob
		{
			m_LaneActions = m_LaneActionQueue.AsReader(),
			m_LaneObjects = m_LaneObjects
		};
		JobHandle dependencies2;
		UpdateTreeObjectsJob jobData2 = new UpdateTreeObjectsJob
		{
			m_TreeActions = m_TreeActionQueue,
			m_SearchTree = m_SearchSystem.GetMovingSearchTree(readOnly: false, out dependencies2)
		};
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(jobData, m_LaneActionQueue.HashRange, 1, dependencies);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(dependencies, dependencies2));
		m_LaneActionQueue.Dispose(jobHandle);
		m_TreeActionQueue.Dispose(jobHandle2);
		m_SearchSystem.AddMovingSearchTreeWriter(jobHandle2);
		return jobHandle;
	}
```

- `public Begin(Unity.Collections.Allocator allocator) : Game.Net.LaneObjectCommandBuffer`  

```csharp
public LaneObjectCommandBuffer Begin(Allocator allocator)
	{
		m_LaneActionQueue = new NativeParallelQueue<LaneObjectAction>(allocator);
		m_TreeActionQueue = new NativeQueue<TreeObjectAction>(allocator);
		return new LaneObjectCommandBuffer(m_LaneActionQueue.AsWriter(), m_TreeActionQueue.AsParallelWriter());
	}
```


## Nested types

- `Game.Net.LaneObjectUpdater+UpdateLaneObjectsJob`  
- `Game.Net.LaneObjectUpdater+UpdateTreeObjectsJob`  

