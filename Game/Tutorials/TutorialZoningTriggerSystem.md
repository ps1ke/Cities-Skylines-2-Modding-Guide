# Game.Tutorials.TutorialZoningTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialZoningTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Game.Prefabs.ZoneSystem m_ZoneSystem;
    private Unity.Entities.EntityQuery m_CreatedZonesQuery;
    private Unity.Entities.EntityQuery m_ZonesQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Tutorials.TutorialZoningTriggerSystem+TypeHandle __TypeHandle;

    public TutorialZoningTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.ZoneSystem m_ZoneSystem`  

```csharp
private Game.Prefabs.ZoneSystem m_ZoneSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedZonesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedZonesQuery;
```

- `private Unity.Entities.EntityQuery m_ZonesQuery`  

```csharp
private Unity.Entities.EntityQuery m_ZonesQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Tutorials.TutorialZoningTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialZoningTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialZoningTriggerSystem()`  

```csharp
[Preserve]
	public TutorialZoningTriggerSystem()
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
		m_ActiveTriggerQuery = GetEntityQuery(ComponentType.ReadOnly<ZoningTriggerData>(), ComponentType.ReadOnly<TriggerActive>(), ComponentType.Exclude<TriggerCompleted>());
		m_CreatedZonesQuery = GetEntityQuery(ComponentType.ReadOnly<Cell>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Created>(), ComponentType.Exclude<Native>());
		m_ZonesQuery = GetEntityQuery(ComponentType.ReadOnly<Cell>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Created>(), ComponentType.Exclude<Native>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		m_ZoneSystem = base.World.GetOrCreateSystemManaged<ZoneSystem>();
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
		if (base.triggersChanged && !m_ZonesQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			CheckZonesJob jobData = new CheckZonesJob
			{
				m_ZoneChunks = m_ZonesQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_CellType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Zones_Cell_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_ZoningTriggerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_ZoningTriggerData_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_UnlockRequirementFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UnlockRequirement_RO_BufferLookup, ref base.CheckedStateRef),
				m_ForcedUnlockDataFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ForceUIGroupUnlockData_RO_BufferLookup, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ZonePrefabs = m_ZoneSystem.GetPrefabs(),
				m_UnlockEventArchetype = m_UnlockEventArchetype,
				m_CommandBuffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter(),
				m_FirstTimeCheck = true
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ActiveTriggerQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
			jobData.m_ZoneChunks.Dispose(base.Dependency);
			m_ZoneSystem.AddPrefabsReader(base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
		else if (!m_CreatedZonesQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle2;
			CheckZonesJob jobData2 = new CheckZonesJob
			{
				m_ZoneChunks = m_CreatedZonesQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2),
				m_CellType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Zones_Cell_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_ZoningTriggerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_ZoningTriggerData_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_UnlockRequirementFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UnlockRequirement_RO_BufferLookup, ref base.CheckedStateRef),
				m_ForcedUnlockDataFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ForceUIGroupUnlockData_RO_BufferLookup, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ZonePrefabs = m_ZoneSystem.GetPrefabs(),
				m_UnlockEventArchetype = m_UnlockEventArchetype,
				m_CommandBuffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter(),
				m_FirstTimeCheck = false
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_ActiveTriggerQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle2));
			jobData2.m_ZoneChunks.Dispose(base.Dependency);
			m_ZoneSystem.AddPrefabsReader(base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialZoningTriggerSystem+CheckZonesJob`  
- `Game.Tutorials.TutorialZoningTriggerSystem+TypeHandle`  

