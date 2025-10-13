# Game.Net.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateCollectSystem : Game.GameSystemBase
{
    private System.Boolean <netsUpdated>k__BackingField;
    private System.Boolean <lanesUpdated>k__BackingField;
    private Unity.Entities.EntityQuery m_NetGeometryQuery;
    private Unity.Entities.EntityQuery m_LaneGeometryQuery;
    private Game.Net.SearchSystem m_SearchSystem;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedNetBounds;
    private Unity.Jobs.JobHandle m_NetWriteDependencies;
    private Unity.Jobs.JobHandle m_NetReadDependencies;
    private Unity.Jobs.JobHandle m_LaneWriteDependencies;
    private Unity.Jobs.JobHandle m_LaneReadDependencies;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedLaneBounds;
    private Game.Net.UpdateCollectSystem+TypeHandle __TypeHandle;

    public System.Boolean netsUpdated { get; private set; }
    public System.Boolean lanesUpdated { get; private set; }

    public UpdateCollectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddLaneBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddNetBoundsReader(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedLaneBounds(Unity.Jobs.JobHandle& dependencies);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedNetBounds(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <netsUpdated>k__BackingField`  

```csharp
private System.Boolean <netsUpdated>k__BackingField;
```

- `private System.Boolean <lanesUpdated>k__BackingField`  

```csharp
private System.Boolean <lanesUpdated>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_NetGeometryQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetGeometryQuery;
```

- `private Unity.Entities.EntityQuery m_LaneGeometryQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneGeometryQuery;
```

- `private Game.Net.SearchSystem m_SearchSystem`  

```csharp
private Game.Net.SearchSystem m_SearchSystem;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedNetBounds`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedNetBounds;
```

- `private Unity.Jobs.JobHandle m_NetWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NetWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_NetReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NetReadDependencies;
```

- `private Unity.Jobs.JobHandle m_LaneWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_LaneWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_LaneReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_LaneReadDependencies;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedLaneBounds`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedLaneBounds;
```

- `private Game.Net.UpdateCollectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.UpdateCollectSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean netsUpdated { get; private set }`  

```csharp
public System.Boolean netsUpdated { get; private set; }
```

- `public System.Boolean lanesUpdated { get; private set }`  

```csharp
public System.Boolean lanesUpdated { get; private set; }
```


## Constructors

- `public UpdateCollectSystem()`  

```csharp
[Preserve]
	public UpdateCollectSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public AddLaneBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddLaneBoundsReader(JobHandle handle)
	{
		m_LaneReadDependencies = JobHandle.CombineDependencies(m_LaneReadDependencies, handle);
	}
```

- `public AddNetBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddNetBoundsReader(JobHandle handle)
	{
		m_NetReadDependencies = JobHandle.CombineDependencies(m_NetReadDependencies, handle);
	}
```

- `public GetUpdatedLaneBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdatedLaneBounds(out JobHandle dependencies)
	{
		dependencies = m_LaneWriteDependencies;
		return m_UpdatedLaneBounds;
	}
```

- `public GetUpdatedNetBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdatedNetBounds(out JobHandle dependencies)
	{
		dependencies = m_NetWriteDependencies;
		return m_UpdatedNetBounds;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_NetGeometryQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<EdgeGeometry>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<NodeGeometry>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_LaneGeometryQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<LaneGeometry>(),
				ComponentType.ReadOnly<UtilityLane>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UpdatedNetBounds = new NativeList<Bounds2>(Allocator.Persistent);
		m_UpdatedLaneBounds = new NativeList<Bounds2>(Allocator.Persistent);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_NetWriteDependencies.Complete();
		m_NetReadDependencies.Complete();
		m_LaneWriteDependencies.Complete();
		m_LaneReadDependencies.Complete();
		m_UpdatedNetBounds.Dispose();
		m_UpdatedLaneBounds.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = !m_NetGeometryQuery.IsEmptyIgnoreFilter;
		bool flag2 = !m_LaneGeometryQuery.IsEmptyIgnoreFilter;
		if (!flag && netsUpdated)
		{
			m_NetWriteDependencies.Complete();
			m_NetReadDependencies.Complete();
			m_UpdatedNetBounds.Clear();
			netsUpdated = false;
		}
		if (!flag2 && lanesUpdated)
		{
			m_LaneWriteDependencies.Complete();
			m_LaneReadDependencies.Complete();
			m_UpdatedLaneBounds.Clear();
			lanesUpdated = false;
		}
		if (flag || flag2)
		{
			JobHandle jobHandle = default(JobHandle);
			if (flag)
			{
				netsUpdated = true;
				NativeQueue<Bounds2> queue = new NativeQueue<Bounds2>(Allocator.TempJob);
				JobHandle dependencies;
				CollectUpdatedNetBoundsJob jobData = new CollectUpdatedNetBoundsJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_StartGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EndGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SearchTree = m_SearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
					m_ResultQueue = queue.AsParallelWriter()
				};
				DequeueBoundsJob jobData2 = new DequeueBoundsJob
				{
					m_Queue = queue,
					m_ResultList = m_UpdatedNetBounds
				};
				JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData, m_NetGeometryQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
				JobHandle jobHandle3 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(jobHandle2, m_NetReadDependencies));
				queue.Dispose(jobHandle3);
				m_SearchSystem.AddNetSearchTreeReader(jobHandle2);
				m_NetWriteDependencies = jobHandle3;
				m_NetReadDependencies = default(JobHandle);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
			if (flag2)
			{
				lanesUpdated = true;
				NativeQueue<Bounds2> queue2 = new NativeQueue<Bounds2>(Allocator.TempJob);
				JobHandle dependencies2;
				CollectUpdatedLaneBoundsJob jobData3 = new CollectUpdatedLaneBoundsJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabLaneGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_SearchTree = m_SearchSystem.GetLaneSearchTree(readOnly: true, out dependencies2),
					m_ResultQueue = queue2.AsParallelWriter()
				};
				DequeueBoundsJob jobData4 = new DequeueBoundsJob
				{
					m_Queue = queue2,
					m_ResultList = m_UpdatedLaneBounds
				};
				JobHandle jobHandle4 = JobChunkExtensions.ScheduleParallel(jobData3, m_LaneGeometryQuery, JobHandle.CombineDependencies(base.Dependency, dependencies2));
				JobHandle jobHandle5 = IJobExtensions.Schedule(jobData4, JobHandle.CombineDependencies(jobHandle4, m_LaneReadDependencies));
				queue2.Dispose(jobHandle5);
				m_SearchSystem.AddLaneSearchTreeReader(jobHandle4);
				m_LaneWriteDependencies = jobHandle5;
				m_LaneReadDependencies = default(JobHandle);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle4);
			}
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Net.UpdateCollectSystem+CollectUpdatedNetBoundsJob`  
- `Game.Net.UpdateCollectSystem+CollectUpdatedLaneBoundsJob`  
- `Game.Net.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Net.UpdateCollectSystem+TypeHandle`  

