# Game.Events.EventJournalInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventJournalInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedEventQuery;
    private Unity.Entities.EntityArchetype m_EventJournalArchetype;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Game.Events.EventJournalInitializeSystem+TypeHandle __TypeHandle;

    public EventJournalInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEventQuery;
```

- `private Unity.Entities.EntityArchetype m_EventJournalArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventJournalArchetype;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Game.Events.EventJournalInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.EventJournalInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EventJournalInitializeSystem()`  

```csharp
[Preserve]
	public EventJournalInitializeSystem()
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
		m_CreatedEventQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<JournalEvent>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EventJournalArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<EventJournalEntry>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<PrefabRef>());
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		RequireForUpdate(m_CreatedEventQuery);
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
		InitEventJournalEntriesJob jobData = new InitEventJournalEntriesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DurationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Duration_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_JournalEventPrefabDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_JournalEventPrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_JournalArchetype = m_EventJournalArchetype,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedEventQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Events.EventJournalInitializeSystem+InitEventJournalEntriesJob`  
- `Game.Events.EventJournalInitializeSystem+TypeHandle`  

