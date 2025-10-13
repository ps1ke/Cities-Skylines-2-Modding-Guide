# Game.Prefabs.NetCompositionMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetCompositionMeshSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_MeshQuery;
    private Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> m_MeshEntities;
    private Unity.Jobs.JobHandle m_Dependencies;
    private Game.Prefabs.NetCompositionMeshSystem+TypeHandle __TypeHandle;

    public NetCompositionMeshSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddMeshEntityReader(Unity.Jobs.JobHandle dependencies);
    public Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> GetMeshEntities(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_MeshQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshQuery;
```

- `private Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> m_MeshEntities`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity> m_MeshEntities;
```

- `private Unity.Jobs.JobHandle m_Dependencies`  

```csharp
private Unity.Jobs.JobHandle m_Dependencies;
```

- `private Game.Prefabs.NetCompositionMeshSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NetCompositionMeshSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetCompositionMeshSystem()`  

```csharp
[Preserve]
	public NetCompositionMeshSystem()
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

- `public AddMeshEntityReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void AddMeshEntityReader(JobHandle dependencies)
	{
		m_Dependencies = dependencies;
	}
```

- `public GetMeshEntities(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeParallelMultiHashMap<System.Int32, Unity.Entities.Entity>`  

```csharp
public NativeParallelMultiHashMap<int, Entity> GetMeshEntities(out JobHandle dependencies)
	{
		dependencies = m_Dependencies;
		return m_MeshEntities;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_MeshQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<NetCompositionMeshData>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_MeshEntities = new NativeParallelMultiHashMap<int, Entity>(100, Allocator.Persistent);
		RequireForUpdate(m_MeshQuery);
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
		m_Dependencies.Complete();
		m_MeshEntities.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.Dependency = (m_Dependencies = JobChunkExtensions.Schedule(new CompositionMeshJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetCompositionMeshDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MeshEntities = m_MeshEntities
		}, m_MeshQuery, JobHandle.CombineDependencies(base.Dependency, m_Dependencies)));
	}
```


## Nested types

- `Game.Prefabs.NetCompositionMeshSystem+CompositionMeshJob`  
- `Game.Prefabs.NetCompositionMeshSystem+TypeHandle`  

