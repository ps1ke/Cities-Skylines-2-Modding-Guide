# Game.Buildings.SchoolUpdatedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SchoolUpdatedSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedSchoolQuery;
    private Unity.Entities.EntityQuery m_DeletedSchoolQuery;
    private Game.Buildings.SchoolUpdatedSystem+TypeHandle __TypeHandle;

    public SchoolUpdatedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedSchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedSchoolQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedSchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedSchoolQuery;
```

- `private Game.Buildings.SchoolUpdatedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.SchoolUpdatedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SchoolUpdatedSystem()`  

```csharp
[Preserve]
	public SchoolUpdatedSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_UpdatedSchoolQuery = GetEntityQuery(ComponentType.ReadOnly<School>(), ComponentType.ReadOnly<Student>(), ComponentType.ReadOnly<StudentsRemoved>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_DeletedSchoolQuery = GetEntityQuery(ComponentType.ReadOnly<School>(), ComponentType.ReadOnly<Student>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		RequireAnyForUpdate(m_UpdatedSchoolQuery, m_DeletedSchoolQuery);
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
		if (!m_UpdatedSchoolQuery.IsEmptyIgnoreFilter)
		{
			SchoolUpdatedJob jobData = new SchoolUpdatedJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_StudentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Student_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_UpdatedSchoolQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		}
		if (!m_DeletedSchoolQuery.IsEmptyIgnoreFilter)
		{
			SchoolDeletedJob jobData2 = new SchoolDeletedJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_StudentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Student_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_Purposes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_DeletedSchoolQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Buildings.SchoolUpdatedSystem+SchoolUpdatedJob`  
- `Game.Buildings.SchoolUpdatedSystem+SchoolDeletedJob`  
- `Game.Buildings.SchoolUpdatedSystem+TypeHandle`  

