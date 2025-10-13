# Game.Serialization.DataMigration.HomelessAndWorkerFixSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HomelessAndWorkerFixSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Unity.Entities.EntityQuery m_WorkerQuery;
    private Unity.Entities.EntityQuery m_HomelessQuery;
    private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery;
    private Unity.Entities.EntityQuery m_AbandonedPropertyQuery;
    private Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle __TypeHandle;

    public HomelessAndWorkerFixSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  

```csharp
private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
```

- `private Unity.Entities.EntityQuery m_WorkerQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkerQuery;
```

- `private Unity.Entities.EntityQuery m_HomelessQuery`  

```csharp
private Unity.Entities.EntityQuery m_HomelessQuery;
```

- `private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery;
```

- `private Unity.Entities.EntityQuery m_AbandonedPropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_AbandonedPropertyQuery;
```

- `private Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HomelessAndWorkerFixSystem()`  

```csharp
[Preserve]
	public HomelessAndWorkerFixSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_DeserializationBarrier = base.World.GetOrCreateSystemManaged<DeserializationBarrier>();
		m_WorkerQuery = GetEntityQuery(ComponentType.ReadOnly<Worker>());
		m_HomelessQuery = GetEntityQuery(ComponentType.ReadOnly<HomelessHousehold>());
		m_AbandonedPropertyQuery = GetEntityQuery(ComponentType.ReadOnly<Abandoned>());
		m_NeedAddPropertySeekerQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Household>(),
				ComponentType.ReadOnly<CompanyData>()
			},
			None = new ComponentType[1] { ComponentType.Exclude<PropertySeeker>() }
		});
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_LoadGameSystem.context.format.Has(FormatTags.HomelessAndWorkerFix))
		{
			if (!m_WorkerQuery.IsEmptyIgnoreFilter)
			{
				JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new WorkerFixJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_WorkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EmployeeBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
					m_CommandBuffer = m_DeserializationBarrier.CreateCommandBuffer().AsParallelWriter()
				}, m_WorkerQuery, base.Dependency);
				m_DeserializationBarrier.AddJobHandleForProducer(jobHandle);
				base.Dependency = jobHandle;
			}
			if (!m_HomelessQuery.IsEmptyIgnoreFilter)
			{
				base.EntityManager.AddComponent<Deleted>(m_HomelessQuery);
			}
			if (!m_NeedAddPropertySeekerQuery.IsEmptyIgnoreFilter)
			{
				JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new AddPropertySeekerJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_CommandBuffer = m_DeserializationBarrier.CreateCommandBuffer().AsParallelWriter()
				}, m_NeedAddPropertySeekerQuery, base.Dependency);
				m_DeserializationBarrier.AddJobHandleForProducer(jobHandle2);
				base.Dependency = jobHandle2;
			}
			if (!m_AbandonedPropertyQuery.IsEmptyIgnoreFilter)
			{
				base.EntityManager.RemoveComponent<PropertyOnMarket>(m_AbandonedPropertyQuery);
			}
		}
	}
```


## Nested types

- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+WorkerFixJob`  
- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+AddPropertySeekerJob`  
- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle`  

