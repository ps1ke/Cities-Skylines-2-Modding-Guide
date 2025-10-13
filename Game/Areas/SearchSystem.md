# Game.Areas.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
    private Unity.Entities.EntityQuery m_AllAreasQuery;
    private Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Areas.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& triangleCount);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
```

- `private Unity.Entities.EntityQuery m_AllAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllAreasQuery;
```

- `private Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount;
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

- `private Game.Areas.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.SearchSystem+TypeHandle __TypeHandle;
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
		m_WriteDependencies = JobHandle.CombineDependencies(m_WriteDependencies, jobHandle);
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

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ> GetSearchTree(bool readOnly, out JobHandle dependencies, out NativeParallelHashMap<Entity, int> triangleCount)
	{
		dependencies = (readOnly ? m_WriteDependencies : JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies));
		triangleCount = m_TriangleCount;
		return m_SearchTree;
	}
```

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& triangleCount) : Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ> GetSearchTree(bool readOnly, out JobHandle dependencies, out NativeParallelHashMap<Entity, int> triangleCount)
	{
		dependencies = (readOnly ? m_WriteDependencies : JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies));
		triangleCount = m_TriangleCount;
		return m_SearchTree;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdatedAreasQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Area>(),
				ComponentType.ReadOnly<Node>(),
				ComponentType.ReadOnly<Triangle>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AllAreasQuery = GetEntityQuery(ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Node>(), ComponentType.ReadOnly<Triangle>(), ComponentType.Exclude<Temp>());
		m_SearchTree = new NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ>(1f, Allocator.Persistent);
		m_TriangleCount = new NativeParallelHashMap<Entity, int>(100, Allocator.Persistent);
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
		m_TriangleCount.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery query = (loaded ? m_AllAreasQuery : m_UpdatedAreasQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			JobHandle dependencies;
			NativeParallelHashMap<Entity, int> triangleCount;
			UpdateSearchTreeJob jobData = new UpdateSearchTreeJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BatchType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Batch_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Loaded = loaded,
				m_SearchTree = GetSearchTree(readOnly: false, out dependencies, out triangleCount),
				m_TriangleCount = triangleCount
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
		NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ> searchTree = GetSearchTree(readOnly: false, out dependencies);
		dependencies.Complete();
		searchTree.Clear();
		m_Loaded = true;
	}
```


## Nested types

- `Game.Areas.SearchSystem+UpdateSearchTreeJob`  
- `Game.Areas.SearchSystem+TypeHandle`  

