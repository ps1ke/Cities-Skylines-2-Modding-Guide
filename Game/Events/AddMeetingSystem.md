# Game.Events.AddMeetingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AddMeetingSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> m_MeetingQueue;
    private Unity.Entities.EntityQuery m_LeisureSettingsQuery;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Jobs.JobHandle m_Deps;
    private Game.Events.AddMeetingSystem+TypeHandle __TypeHandle;

    public AddMeetingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddWriter(Unity.Jobs.JobHandle reader);
    public Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> GetMeetingQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> m_MeetingQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> m_MeetingQueue;
```

- `private Unity.Entities.EntityQuery m_LeisureSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureSettingsQuery;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Jobs.JobHandle m_Deps`  

```csharp
private Unity.Jobs.JobHandle m_Deps;
```

- `private Game.Events.AddMeetingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.AddMeetingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AddMeetingSystem()`  

```csharp
[Preserve]
	public AddMeetingSystem()
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

- `public AddWriter(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public void AddWriter(JobHandle reader)
	{
		m_Deps = JobHandle.CombineDependencies(m_Deps, reader);
	}
```

- `public GetMeetingQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting>`  

```csharp
public NativeQueue<AddMeeting> GetMeetingQueue(out JobHandle deps)
	{
		deps = m_Deps;
		return m_MeetingQueue;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier1>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_LeisureSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<LeisureParametersData>());
		m_JournalDataArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<AddEventJournalData>(), ComponentType.ReadWrite<Game.Common.Event>());
		m_MeetingQueue = new NativeQueue<AddMeeting>(Allocator.Persistent);
		RequireForUpdate(m_LeisureSettingsQuery);
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
		m_MeetingQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		TravelJob jobData = new TravelJob
		{
			m_MeetingQueue = m_MeetingQueue,
			m_AttendingEvents = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_AttendingEvent_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EventDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EventData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HaveCoordinatedMeetings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_HaveCoordinatedMeetingData_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_LeisureParameters = m_LeisureSettingsQuery.GetSingleton<LeisureParametersData>(),
			m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Targets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(m_Deps, base.Dependency));
		AddWriter(base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Events.AddMeetingSystem+AddMeeting`  
- `Game.Events.AddMeetingSystem+TravelJob`  
- `Game.Events.AddMeetingSystem+TypeHandle`  

