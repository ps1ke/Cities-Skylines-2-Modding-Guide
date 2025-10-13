# Game.Zones.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateCollectSystem : Game.GameSystemBase
{
    private System.Boolean <isUpdated>k__BackingField;
    private Unity.Entities.EntityQuery m_BlockQuery;
    private Game.Zones.SearchSystem m_SearchSystem;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedBounds;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Game.Zones.UpdateCollectSystem+TypeHandle __TypeHandle;

    public System.Boolean isUpdated { get; private set; }

    public UpdateCollectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddBoundsWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedBounds(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <isUpdated>k__BackingField`  

```csharp
private System.Boolean <isUpdated>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_BlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_BlockQuery;
```

- `private Game.Zones.SearchSystem m_SearchSystem`  

```csharp
private Game.Zones.SearchSystem m_SearchSystem;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedBounds`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedBounds;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Game.Zones.UpdateCollectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Zones.UpdateCollectSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean isUpdated { get; private set }`  

```csharp
public System.Boolean isUpdated { get; private set; }
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

- `public AddBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddBoundsReader(JobHandle handle)
	{
		m_ReadDependencies = JobHandle.CombineDependencies(m_ReadDependencies, handle);
	}
```

- `public AddBoundsWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddBoundsWriter(JobHandle handle)
	{
		m_WriteDependencies = handle;
		m_ReadDependencies = default(JobHandle);
	}
```

- `public GetUpdatedBounds(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdatedBounds(bool readOnly, out JobHandle dependencies)
	{
		if (readOnly)
		{
			dependencies = m_WriteDependencies;
		}
		else
		{
			dependencies = JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies);
			isUpdated = true;
		}
		return m_UpdatedBounds;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_BlockQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Block>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UpdatedBounds = new NativeList<Bounds2>(Allocator.Persistent);
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
		m_WriteDependencies.Complete();
		m_ReadDependencies.Complete();
		m_UpdatedBounds.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_BlockQuery.IsEmptyIgnoreFilter)
		{
			m_WriteDependencies.Complete();
			m_ReadDependencies.Complete();
			m_UpdatedBounds.Clear();
			isUpdated = false;
			return;
		}
		isUpdated = true;
		NativeQueue<Bounds2> queue = new NativeQueue<Bounds2>(Allocator.TempJob);
		JobHandle dependencies;
		CollectUpdatedBlockBoundsJob jobData = new CollectUpdatedBlockBoundsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_Block_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SearchTree = m_SearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_ResultQueue = queue.AsParallelWriter()
		};
		DequeueBoundsJob jobData2 = new DequeueBoundsJob
		{
			m_Queue = queue,
			m_ResultList = m_UpdatedBounds
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_BlockQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(jobHandle, m_WriteDependencies, m_ReadDependencies));
		queue.Dispose(jobHandle2);
		m_SearchSystem.AddSearchTreeReader(jobHandle);
		m_WriteDependencies = jobHandle2;
		m_ReadDependencies = default(JobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Zones.UpdateCollectSystem+CollectUpdatedBlockBoundsJob`  
- `Game.Zones.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Zones.UpdateCollectSystem+TypeHandle`  

