# Game.Objects.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateCollectSystem : Game.GameSystemBase
{
    private System.Boolean <isUpdated>k__BackingField;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_UpdatedBounds;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Game.Objects.UpdateCollectSystem+TypeHandle __TypeHandle;

    public System.Boolean isUpdated { get; private set; }

    public UpdateCollectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddBoundsReader(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedBounds(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <isUpdated>k__BackingField`  

```csharp
private System.Boolean <isUpdated>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
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

- `private Game.Objects.UpdateCollectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.UpdateCollectSystem+TypeHandle __TypeHandle;
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

- `public GetUpdatedBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdatedBounds(out JobHandle dependencies)
	{
		dependencies = m_WriteDependencies;
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
		m_ObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Object>(),
				ComponentType.ReadOnly<Static>(),
				ComponentType.ReadOnly<Transform>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UpdatedBounds = new NativeList<Bounds2>(Allocator.Persistent);
		RequireForUpdate(m_ObjectQuery);
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
		m_UpdatedBounds.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		m_WriteDependencies.Complete();
		m_ReadDependencies.Complete();
		m_UpdatedBounds.Clear();
		isUpdated = false;
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		isUpdated = true;
		NativeQueue<Bounds2> queue = new NativeQueue<Bounds2>(Allocator.TempJob);
		JobHandle dependencies;
		CollectUpdatedObjectBoundsJob jobData = new CollectUpdatedObjectBoundsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SearchTree = m_SearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_ResultQueue = queue.AsParallelWriter()
		};
		DequeueBoundsJob jobData2 = new DequeueBoundsJob
		{
			m_Queue = queue,
			m_ResultList = m_UpdatedBounds
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_ObjectQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(jobHandle, m_ReadDependencies));
		queue.Dispose(jobHandle2);
		m_SearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_WriteDependencies = jobHandle2;
		m_ReadDependencies = default(JobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Objects.UpdateCollectSystem+CollectUpdatedObjectBoundsJob`  
- `Game.Objects.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Objects.UpdateCollectSystem+TypeHandle`  

