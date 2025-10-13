# Game.Routes.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
    private Unity.Entities.EntityQuery m_AllRoutesQuery;
    private Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_ElementCount;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Routes.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
```

- `private Unity.Entities.EntityQuery m_AllRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllRoutesQuery;
```

- `private Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_ElementCount`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_ElementCount;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Routes.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.SearchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SearchSystem()`  

```csharp
[Preserve]
	public SearchSystem()
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

- `public AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddSearchTreeReader(JobHandle jobHandle)
	{
		m_ReadDependencies = JobHandle.CombineDependencies(m_ReadDependencies, jobHandle);
	}
```

- `public AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddSearchTreeWriter(JobHandle jobHandle)
	{
		m_WriteDependencies = jobHandle;
	}
```

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public NativeQuadTree<RouteSearchItem, QuadTreeBoundsXZ> GetSearchTree(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_WriteDependencies : JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies));
		return m_SearchTree;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdatedRoutesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Waypoint>(),
				ComponentType.ReadOnly<Position>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Segment>(),
				ComponentType.ReadOnly<PathElement>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Event>(),
				ComponentType.ReadOnly<PathUpdated>()
			}
		});
		m_AllRoutesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Waypoint>(),
				ComponentType.ReadOnly<Position>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Segment>(),
				ComponentType.ReadOnly<PathElement>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_SearchTree = new NativeQuadTree<RouteSearchItem, QuadTreeBoundsXZ>(1f, Allocator.Persistent);
		m_ElementCount = new NativeParallelHashMap<Entity, int>(100, Allocator.Persistent);
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
		m_SearchTree.Dispose();
		m_ElementCount.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery query = (loaded ? m_AllRoutesQuery : m_UpdatedRoutesQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			JobHandle dependencies;
			UpdateSearchTreeJob jobData = new UpdateSearchTreeJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Position_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PathUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurveElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_CurveElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SegmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_CurveElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Loaded = loaded,
				m_SearchTree = GetSearchTree(readOnly: false, out dependencies),
				m_ElementCount = m_ElementCount
			};
			base.Dependency = JobChunkExtensions.Schedule(jobData, query, JobHandle.CombineDependencies(base.Dependency, dependencies));
			AddSearchTreeWriter(base.Dependency);
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		JobHandle dependencies;
		NativeQuadTree<RouteSearchItem, QuadTreeBoundsXZ> searchTree = GetSearchTree(readOnly: false, out dependencies);
		dependencies.Complete();
		searchTree.Clear();
		m_Loaded = true;
	}
```


## Nested types

- `Game.Routes.SearchSystem+UpdateSearchTreeJob`  
- `Game.Routes.SearchSystem+TypeHandle`  

