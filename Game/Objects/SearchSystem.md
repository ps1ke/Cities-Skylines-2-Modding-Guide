# Game.Objects.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_UpdatedStaticsQuery;
    private Unity.Entities.EntityQuery m_AllStaticsQuery;
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticSearchTree;
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingSearchTree;
    private Unity.Jobs.JobHandle m_StaticReadDependencies;
    private Unity.Jobs.JobHandle m_StaticWriteDependencies;
    private Unity.Jobs.JobHandle m_MovingReadDependencies;
    private Unity.Jobs.JobHandle m_MovingWriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Objects.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddMovingSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddMovingSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddStaticSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddStaticSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetMovingSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> GetStaticSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedStaticsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedStaticsQuery;
```

- `private Unity.Entities.EntityQuery m_AllStaticsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllStaticsQuery;
```

- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticSearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticSearchTree;
```

- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingSearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingSearchTree;
```

- `private Unity.Jobs.JobHandle m_StaticReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_StaticReadDependencies;
```

- `private Unity.Jobs.JobHandle m_StaticWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_StaticWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_MovingReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_MovingReadDependencies;
```

- `private Unity.Jobs.JobHandle m_MovingWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_MovingWriteDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Objects.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SearchSystem+TypeHandle __TypeHandle;
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

- `public AddMovingSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddMovingSearchTreeReader(JobHandle jobHandle)
	{
		m_MovingReadDependencies = JobHandle.CombineDependencies(m_MovingReadDependencies, jobHandle);
	}
```

- `public AddMovingSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddMovingSearchTreeWriter(JobHandle jobHandle)
	{
		m_MovingWriteDependencies = jobHandle;
	}
```

- `public AddStaticSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddStaticSearchTreeReader(JobHandle jobHandle)
	{
		m_StaticReadDependencies = JobHandle.CombineDependencies(m_StaticReadDependencies, jobHandle);
	}
```

- `public AddStaticSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddStaticSearchTreeWriter(JobHandle jobHandle)
	{
		m_StaticWriteDependencies = jobHandle;
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

- `public GetMovingSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public NativeQuadTree<Entity, QuadTreeBoundsXZ> GetMovingSearchTree(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_MovingWriteDependencies : JobHandle.CombineDependencies(m_MovingReadDependencies, m_MovingWriteDependencies));
		return m_MovingSearchTree;
	}
```

- `public GetStaticSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public NativeQuadTree<Entity, QuadTreeBoundsXZ> GetStaticSearchTree(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_StaticWriteDependencies : JobHandle.CombineDependencies(m_StaticReadDependencies, m_StaticWriteDependencies));
		return m_StaticSearchTree;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_UpdatedStaticsQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Object>(),
				ComponentType.ReadOnly<Static>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AllStaticsQuery = GetEntityQuery(ComponentType.ReadOnly<Object>(), ComponentType.ReadOnly<Static>(), ComponentType.Exclude<Temp>());
		m_StaticSearchTree = new NativeQuadTree<Entity, QuadTreeBoundsXZ>(1f, Allocator.Persistent);
		m_MovingSearchTree = new NativeQuadTree<Entity, QuadTreeBoundsXZ>(1f, Allocator.Persistent);
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
		m_StaticReadDependencies.Complete();
		m_StaticWriteDependencies.Complete();
		m_StaticSearchTree.Dispose();
		m_MovingReadDependencies.Complete();
		m_MovingWriteDependencies.Complete();
		m_MovingSearchTree.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery query = (loaded ? m_AllStaticsQuery : m_UpdatedStaticsQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			JobHandle dependencies;
			UpdateSearchTreeJob jobData = new UpdateSearchTreeJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TreeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OverriddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_Loaded = loaded,
				m_SearchTree = GetStaticSearchTree(readOnly: false, out dependencies)
			};
			base.Dependency = JobChunkExtensions.Schedule(jobData, query, JobHandle.CombineDependencies(base.Dependency, dependencies));
			AddStaticSearchTreeWriter(base.Dependency);
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		JobHandle dependencies;
		NativeQuadTree<Entity, QuadTreeBoundsXZ> staticSearchTree = GetStaticSearchTree(readOnly: false, out dependencies);
		JobHandle dependencies2;
		NativeQuadTree<Entity, QuadTreeBoundsXZ> movingSearchTree = GetMovingSearchTree(readOnly: false, out dependencies2);
		dependencies.Complete();
		dependencies2.Complete();
		staticSearchTree.Clear();
		movingSearchTree.Clear();
		m_Loaded = true;
	}
```


## Nested types

- `Game.Objects.SearchSystem+UpdateSearchTreeJob`  
- `Game.Objects.SearchSystem+TypeHandle`  

