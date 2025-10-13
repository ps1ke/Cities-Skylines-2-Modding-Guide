# Game.Prefabs.TriggerPrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TriggerPrefabSystem : Game.GameSystemBase
{
    private Game.Prefabs.TriggerPrefabData m_PrefabData;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Game.Prefabs.TriggerPrefabSystem+TypeHandle __TypeHandle;

    public TriggerPrefabSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle handle);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public Game.Prefabs.TriggerPrefabData ReadTriggerPrefabData(Unity.Jobs.JobHandle& dependencies);
}
```


## Fields

- `private Game.Prefabs.TriggerPrefabData m_PrefabData`  

```csharp
private Game.Prefabs.TriggerPrefabData m_PrefabData;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Game.Prefabs.TriggerPrefabSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.TriggerPrefabSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TriggerPrefabSystem()`  

```csharp
[Preserve]
	public TriggerPrefabSystem()
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

- `public AddReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddReader(JobHandle handle)
	{
		m_ReadDependencies = JobHandle.CombineDependencies(m_ReadDependencies, handle);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<TriggerData>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_PrefabData = new TriggerPrefabData(Allocator.Persistent);
		RequireForUpdate(m_PrefabQuery);
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
		m_PrefabData.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle jobHandle = JobChunkExtensions.Schedule(new UpdateTriggerPrefabDataJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TriggerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_TriggerData_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TriggerPrefabData = m_PrefabData
		}, m_PrefabQuery, JobHandle.CombineDependencies(base.Dependency, m_ReadDependencies));
		m_ReadDependencies = default(JobHandle);
		m_WriteDependencies = jobHandle;
		base.Dependency = jobHandle;
	}
```

- `public ReadTriggerPrefabData(Unity.Jobs.JobHandle& dependencies) : Game.Prefabs.TriggerPrefabData`  

```csharp
public TriggerPrefabData ReadTriggerPrefabData(out JobHandle dependencies)
	{
		dependencies = m_WriteDependencies;
		return m_PrefabData;
	}
```


## Nested types

- `Game.Prefabs.TriggerPrefabSystem+UpdateTriggerPrefabDataJob`  
- `Game.Prefabs.TriggerPrefabSystem+TypeHandle`  

