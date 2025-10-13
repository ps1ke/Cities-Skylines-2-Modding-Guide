# Game.Debug.SearchTreeDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class SearchTreeDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Routes.SearchSystem m_RouteSearchSystem;
    private Game.Effects.SearchSystem m_EffectSearchSystem;
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_StaticObjectOption;
    private Game.Debug.BaseDebugSystem+Option m_MovingObjectOption;
    private Game.Debug.BaseDebugSystem+Option m_NetOption;
    private Game.Debug.BaseDebugSystem+Option m_LaneOption;
    private Game.Debug.BaseDebugSystem+Option m_ZoneOption;
    private Game.Debug.BaseDebugSystem+Option m_AreaOption;
    private Game.Debug.BaseDebugSystem+Option m_RouteOption;
    private Game.Debug.BaseDebugSystem+Option m_EffectOption;
    private Game.Debug.BaseDebugSystem+Option m_LocalEffectOption;

    public SearchTreeDebugSystem();

    private Unity.Jobs.JobHandle AreaSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle EffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle LaneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle LocalEffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle MovingObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle NetSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle RouteSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle StaticObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle ZoneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
}
```


## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Routes.SearchSystem m_RouteSearchSystem`  

```csharp
private Game.Routes.SearchSystem m_RouteSearchSystem;
```

- `private Game.Effects.SearchSystem m_EffectSearchSystem`  

```csharp
private Game.Effects.SearchSystem m_EffectSearchSystem;
```

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_StaticObjectOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StaticObjectOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MovingObjectOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MovingObjectOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_NetOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_NetOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LaneOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LaneOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ZoneOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ZoneOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_AreaOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AreaOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_RouteOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_RouteOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_EffectOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_EffectOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LocalEffectOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LocalEffectOption;
```


## Constructors

- `public SearchTreeDebugSystem()`  

```csharp
[Preserve]
	public SearchTreeDebugSystem()
	{
	}
```


## Methods

- `private AreaSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle AreaSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<AreaSearchItem, QuadTreeBoundsXZ, QuadTreeBoundsXZ.DebugIterator<AreaSearchItem>>
		{
			m_Tree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_Iterator = new QuadTreeBoundsXZ.DebugIterator<AreaSearchItem>(bounds, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `private EffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle EffectSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<SourceInfo, QuadTreeBoundsXZ, QuadTreeBoundsXZ.DebugIterator<SourceInfo>>
		{
			m_Tree = m_EffectSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_Iterator = new QuadTreeBoundsXZ.DebugIterator<SourceInfo>(bounds, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_EffectSearchSystem.AddSearchTreeReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `private LaneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle LaneSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<Entity, QuadTreeBoundsXZ, QuadTreeBoundsXZ.DebugIterator<Entity>>
		{
			m_Tree = m_NetSearchSystem.GetLaneSearchTree(readOnly: true, out dependencies),
			m_Iterator = new QuadTreeBoundsXZ.DebugIterator<Entity>(bounds, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_NetSearchSystem.AddLaneSearchTreeReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `private LocalEffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle LocalEffectSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<LocalEffectSystem.EffectItem, LocalEffectSystem.EffectBounds, LocalEffectDebugIterator>
		{
			m_Tree = m_LocalEffectSystem.GetSearchTree(readOnly: true, out dependencies),
			m_Iterator = new LocalEffectDebugIterator(bounds.xz, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_LocalEffectSystem.AddLocalEffectReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `private MovingObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle MovingObjectSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<Entity, QuadTreeBoundsXZ, QuadTreeBoundsXZ.DebugIterator<Entity>>
		{
			m_Tree = m_ObjectSearchSystem.GetMovingSearchTree(readOnly: true, out dependencies),
			m_Iterator = new QuadTreeBoundsXZ.DebugIterator<Entity>(bounds, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_ObjectSearchSystem.AddMovingSearchTreeReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `private NetSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle NetSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<Entity, QuadTreeBoundsXZ, QuadTreeBoundsXZ.DebugIterator<Entity>>
		{
			m_Tree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_Iterator = new QuadTreeBoundsXZ.DebugIterator<Entity>(bounds, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ZoneSearchSystem = base.World.GetOrCreateSystemManaged<Game.Zones.SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_RouteSearchSystem = base.World.GetOrCreateSystemManaged<Game.Routes.SearchSystem>();
		m_EffectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Effects.SearchSystem>();
		m_LocalEffectSystem = base.World.GetOrCreateSystemManaged<LocalEffectSystem>();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_StaticObjectOption = AddOption("Static Objects", defaultEnabled: true);
		m_MovingObjectOption = AddOption("Moving Objects", defaultEnabled: true);
		m_NetOption = AddOption("Nets", defaultEnabled: false);
		m_LaneOption = AddOption("Lanes", defaultEnabled: false);
		m_ZoneOption = AddOption("Zones", defaultEnabled: false);
		m_AreaOption = AddOption("Areas", defaultEnabled: false);
		m_RouteOption = AddOption("Routes", defaultEnabled: false);
		m_EffectOption = AddOption("Effects", defaultEnabled: false);
		m_LocalEffectOption = AddOption("Local Effects", defaultEnabled: false);
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		Bounds3 bounds = new Bounds3(float.MinValue, float.MaxValue);
		JobHandle jobHandle = inputDeps;
		if (m_StaticObjectOption.enabled)
		{
			JobHandle job = StaticObjectSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job);
		}
		if (m_MovingObjectOption.enabled)
		{
			JobHandle job2 = MovingObjectSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job2);
		}
		if (m_NetOption.enabled)
		{
			JobHandle job3 = NetSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job3);
		}
		if (m_LaneOption.enabled)
		{
			JobHandle job4 = LaneSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job4);
		}
		if (m_ZoneOption.enabled)
		{
			JobHandle job5 = ZoneSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job5);
		}
		if (m_AreaOption.enabled)
		{
			JobHandle job6 = AreaSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job6);
		}
		if (m_RouteOption.enabled)
		{
			JobHandle job7 = RouteSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job7);
		}
		if (m_EffectOption.enabled)
		{
			JobHandle job8 = EffectSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job8);
		}
		if (m_LocalEffectOption.enabled)
		{
			JobHandle job9 = LocalEffectSearchTreeDebug(inputDeps, bounds);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job9);
		}
		return jobHandle;
	}
```

- `private RouteSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle RouteSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<RouteSearchItem, QuadTreeBoundsXZ, QuadTreeBoundsXZ.DebugIterator<RouteSearchItem>>
		{
			m_Tree = m_RouteSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_Iterator = new QuadTreeBoundsXZ.DebugIterator<RouteSearchItem>(bounds, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_RouteSearchSystem.AddSearchTreeReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `private StaticObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle StaticObjectSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<Entity, QuadTreeBoundsXZ, QuadTreeBoundsXZ.DebugIterator<Entity>>
		{
			m_Tree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_Iterator = new QuadTreeBoundsXZ.DebugIterator<Entity>(bounds, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `private ZoneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle ZoneSearchTreeDebug(JobHandle inputDeps, Bounds3 bounds)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new NativeQuadTreeGizmoJob<Entity, Bounds2, Bounds2DebugIterator<Entity>>
		{
			m_Tree = m_ZoneSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_Iterator = new Bounds2DebugIterator<Entity>(bounds.xz, m_GizmosSystem.GetGizmosBatcher(out dependencies2))
		}, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_ZoneSearchSystem.AddSearchTreeReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.SearchTreeDebugSystem+NativeQuadTreeGizmoJob<TItem, TBounds, TIterator>`  
- `Game.Debug.SearchTreeDebugSystem+Bounds2DebugIterator<TItem>`  
- `Game.Debug.SearchTreeDebugSystem+LocalEffectDebugIterator`  

