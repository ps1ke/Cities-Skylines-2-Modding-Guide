# Game.Areas.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateCollectSystem : Game.GameSystemBase
{
    private Game.Areas.SearchSystem m_SearchSystem;
    private Game.Areas.UpdateCollectSystem+UpdateBufferData m_LotData;
    private Game.Areas.UpdateCollectSystem+UpdateBufferData m_DistrictData;
    private Game.Areas.UpdateCollectSystem+UpdateBufferData m_MapTileData;
    private Game.Areas.UpdateCollectSystem+UpdateBufferData m_SpaceData;
    private Game.Areas.UpdateCollectSystem+TypeHandle __TypeHandle;

    public System.Boolean lotsUpdated { get; }
    public System.Boolean districtsUpdated { get; }
    public System.Boolean mapTilesUpdated { get; }
    public System.Boolean spacesUpdated { get; }

    public UpdateCollectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddDistrictBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddLotBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddMapTileBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddSpaceBoundsReader(Unity.Jobs.JobHandle handle);
    private Unity.Entities.EntityQuery GetQuery<T>();
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedDistrictBounds(Unity.Jobs.JobHandle& dependencies);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedLotBounds(Unity.Jobs.JobHandle& dependencies);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedMapTileBounds(Unity.Jobs.JobHandle& dependencies);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedSpaceBounds(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    private Unity.Jobs.JobHandle UpdateBounds(Game.Areas.UpdateCollectSystem+UpdateBufferData& data, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Areas.SearchSystem m_SearchSystem`  

```csharp
private Game.Areas.SearchSystem m_SearchSystem;
```

- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_LotData`  

```csharp
private Game.Areas.UpdateCollectSystem+UpdateBufferData m_LotData;
```

- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_DistrictData`  

```csharp
private Game.Areas.UpdateCollectSystem+UpdateBufferData m_DistrictData;
```

- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_MapTileData`  

```csharp
private Game.Areas.UpdateCollectSystem+UpdateBufferData m_MapTileData;
```

- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_SpaceData`  

```csharp
private Game.Areas.UpdateCollectSystem+UpdateBufferData m_SpaceData;
```

- `private Game.Areas.UpdateCollectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.UpdateCollectSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean lotsUpdated { get }`  

```csharp
public System.Boolean lotsUpdated { get; }
```

- `public System.Boolean districtsUpdated { get }`  

```csharp
public System.Boolean districtsUpdated { get; }
```

- `public System.Boolean mapTilesUpdated { get }`  

```csharp
public System.Boolean mapTilesUpdated { get; }
```

- `public System.Boolean spacesUpdated { get }`  

```csharp
public System.Boolean spacesUpdated { get; }
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

- `public AddDistrictBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddDistrictBoundsReader(JobHandle handle)
	{
		m_DistrictData.m_ReadDependencies = JobHandle.CombineDependencies(m_DistrictData.m_ReadDependencies, handle);
	}
```

- `public AddLotBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddLotBoundsReader(JobHandle handle)
	{
		m_LotData.m_ReadDependencies = JobHandle.CombineDependencies(m_LotData.m_ReadDependencies, handle);
	}
```

- `public AddMapTileBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddMapTileBoundsReader(JobHandle handle)
	{
		m_MapTileData.m_ReadDependencies = JobHandle.CombineDependencies(m_MapTileData.m_ReadDependencies, handle);
	}
```

- `public AddSpaceBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddSpaceBoundsReader(JobHandle handle)
	{
		m_SpaceData.m_ReadDependencies = JobHandle.CombineDependencies(m_SpaceData.m_ReadDependencies, handle);
	}
```

- `private GetQuery<T>() : Unity.Entities.EntityQuery`  

```csharp
private Unity.Entities.EntityQuery GetQuery<T>();
```

- `public GetUpdatedDistrictBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdatedDistrictBounds(out JobHandle dependencies)
	{
		dependencies = m_DistrictData.m_WriteDependencies;
		return m_DistrictData.m_Bounds;
	}
```

- `public GetUpdatedLotBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdatedLotBounds(out JobHandle dependencies)
	{
		dependencies = m_LotData.m_WriteDependencies;
		return m_LotData.m_Bounds;
	}
```

- `public GetUpdatedMapTileBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdatedMapTileBounds(out JobHandle dependencies)
	{
		dependencies = m_MapTileData.m_WriteDependencies;
		return m_MapTileData.m_Bounds;
	}
```

- `public GetUpdatedSpaceBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdatedSpaceBounds(out JobHandle dependencies)
	{
		dependencies = m_SpaceData.m_WriteDependencies;
		return m_SpaceData.m_Bounds;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_LotData.Create(GetQuery<Lot>());
		m_DistrictData.Create(GetQuery<District>());
		m_MapTileData.Create(GetQuery<MapTile>());
		m_SpaceData.Create(GetQuery<Space>());
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
		m_LotData.Dispose();
		m_DistrictData.Dispose();
		m_MapTileData.Dispose();
		m_SpaceData.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		m_LotData.Clear();
		m_DistrictData.Clear();
		m_MapTileData.Clear();
		m_SpaceData.Clear();
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependency = base.Dependency;
		if (m_LotData.m_Query.IsEmptyIgnoreFilter)
		{
			m_LotData.Clear();
		}
		else
		{
			JobHandle job = UpdateBounds(ref m_LotData, dependency);
			base.Dependency = JobHandle.CombineDependencies(base.Dependency, job);
		}
		if (m_DistrictData.m_Query.IsEmptyIgnoreFilter)
		{
			m_DistrictData.Clear();
		}
		else
		{
			JobHandle job2 = UpdateBounds(ref m_DistrictData, dependency);
			base.Dependency = JobHandle.CombineDependencies(base.Dependency, job2);
		}
		if (m_MapTileData.m_Query.IsEmptyIgnoreFilter)
		{
			m_MapTileData.Clear();
		}
		else
		{
			JobHandle job3 = UpdateBounds(ref m_MapTileData, dependency);
			base.Dependency = JobHandle.CombineDependencies(base.Dependency, job3);
		}
		if (m_SpaceData.m_Query.IsEmptyIgnoreFilter)
		{
			m_SpaceData.Clear();
			return;
		}
		JobHandle job4 = UpdateBounds(ref m_SpaceData, dependency);
		base.Dependency = JobHandle.CombineDependencies(base.Dependency, job4);
	}
```

- `private UpdateBounds(Game.Areas.UpdateCollectSystem+UpdateBufferData& data, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateBounds(ref UpdateBufferData data, JobHandle inputDeps)
	{
		data.m_IsUpdated = true;
		NativeQueue<Bounds2> queue = new NativeQueue<Bounds2>(Allocator.TempJob);
		JobHandle dependencies;
		NativeParallelHashMap<Entity, int> triangleCount;
		NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ> searchTree = m_SearchSystem.GetSearchTree(readOnly: true, out dependencies, out triangleCount);
		CollectUpdatedAreaBoundsJob jobData = new CollectUpdatedAreaBoundsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SearchTree = searchTree,
			m_TriangleCount = triangleCount,
			m_ResultQueue = queue.AsParallelWriter()
		};
		DequeueBoundsJob jobData2 = new DequeueBoundsJob
		{
			m_Queue = queue,
			m_ResultList = data.m_Bounds
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, data.m_Query, JobHandle.CombineDependencies(inputDeps, dependencies));
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(jobHandle, data.m_ReadDependencies));
		queue.Dispose(jobHandle2);
		m_SearchSystem.AddSearchTreeReader(jobHandle);
		data.m_WriteDependencies = jobHandle2;
		data.m_ReadDependencies = default(JobHandle);
		return jobHandle2;
	}
```


## Nested types

- `Game.Areas.UpdateCollectSystem+UpdateBufferData`  
- `Game.Areas.UpdateCollectSystem+CollectUpdatedAreaBoundsJob`  
- `Game.Areas.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Areas.UpdateCollectSystem+TypeHandle`  

