# Game.Tutorials.TutorialAreaTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialAreaTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Unity.Entities.EntityQuery m_AreaModificationQuery;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Tutorials.TutorialAreaTriggerSystem+TypeHandle __TypeHandle;

    public TutorialAreaTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AreaModificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaModificationQuery;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Tutorials.TutorialAreaTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialAreaTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialAreaTriggerSystem()`  

```csharp
[Preserve]
	public TutorialAreaTriggerSystem()
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
		m_AreaModificationQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Native>());
		m_AreaQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Area>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Native>());
		m_ActiveTriggerQuery = GetEntityQuery(ComponentType.ReadOnly<AreaTriggerData>(), ComponentType.ReadOnly<TriggerActive>(), ComponentType.Exclude<TriggerCompleted>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		RequireForUpdate(m_ActiveTriggerQuery);
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
		base.OnUpdate();
		if (base.triggersChanged)
		{
			JobHandle outJobHandle;
			CheckModifiedAreasJob jobData = new CheckModifiedAreasJob
			{
				m_AreaModificationChunks = m_AreaQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_TriggerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_AreaTriggerData_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_UnlockRequirementFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UnlockRequirement_RO_BufferLookup, ref base.CheckedStateRef),
				m_ForcedUnlockDataFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ForceUIGroupUnlockData_RO_BufferLookup, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Updated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UnlockEventArchetype = m_UnlockEventArchetype,
				m_CommandBuffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter(),
				m_FirstTimeCheck = true
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ActiveTriggerQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
			jobData.m_AreaModificationChunks.Dispose(base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
		else if (!m_AreaModificationQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle2;
			CheckModifiedAreasJob jobData2 = new CheckModifiedAreasJob
			{
				m_AreaModificationChunks = m_AreaModificationQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2),
				m_TriggerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_AreaTriggerData_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_UnlockRequirementFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UnlockRequirement_RO_BufferLookup, ref base.CheckedStateRef),
				m_ForcedUnlockDataFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ForceUIGroupUnlockData_RO_BufferLookup, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Updated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UnlockEventArchetype = m_UnlockEventArchetype,
				m_CommandBuffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter(),
				m_FirstTimeCheck = false
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_ActiveTriggerQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle2));
			jobData2.m_AreaModificationChunks.Dispose(base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialAreaTriggerSystem+CheckModifiedAreasJob`  
- `Game.Tutorials.TutorialAreaTriggerSystem+TypeHandle`  

