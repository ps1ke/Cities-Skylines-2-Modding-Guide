# Game.Simulation.FindEventAttendantsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FindEventAttendantsSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Collections.NativeQueue<Game.Simulation.FindEventAttendantsSystem+Attend> m_AttendQueue;
    private Unity.Entities.EntityArchetype m_MeetingArchetype;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Game.Simulation.FindEventAttendantsSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public FindEventAttendantsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.FindEventAttendantsSystem+Attend> m_AttendQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.FindEventAttendantsSystem+Attend> m_AttendQueue;
```

- `private Unity.Entities.EntityArchetype m_MeetingArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MeetingArchetype;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Game.Simulation.FindEventAttendantsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FindEventAttendantsSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public FindEventAttendantsSystem()`  

```csharp
[Preserve]
	public FindEventAttendantsSystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_EventQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Events.CalendarEvent>(), ComponentType.ReadWrite<FindingEventParticipants>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_HouseholdQuery = GetEntityQuery(ComponentType.ReadWrite<Household>(), ComponentType.ReadWrite<UpdateFrame>(), ComponentType.ReadWrite<HouseholdCitizen>(), ComponentType.Exclude<AttendingEvent>(), ComponentType.Exclude<Deleted>());
		m_AttendQueue = new NativeQueue<Attend>(Allocator.Persistent);
		m_MeetingArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<CoordinatedMeeting>(), ComponentType.ReadWrite<CoordinatedMeetingAttendee>(), ComponentType.ReadWrite<PrefabRef>(), ComponentType.ReadWrite<Created>());
		m_JournalDataArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<AddEventJournalData>(), ComponentType.ReadWrite<Game.Common.Event>());
		RequireForUpdate(m_EventQuery);
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
		base.OnDestroy();
		m_AttendQueue.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		JobHandle outJobHandle;
		ConsiderAttendanceJob jobData = new ConsiderAttendanceJob
		{
			m_EventEntities = m_EventQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizenType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CommuterHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CommuterHousehold_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameIndex = updateFrameWithInterval,
			m_CitizenDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Events = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CalendarEventData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttendQueue = m_AttendQueue.AsParallelWriter(),
			m_RandomSeed = RandomSeed.Next(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_HouseholdQuery, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
		AttendJob jobData2 = new AttendJob
		{
			m_EventEntities = m_EventQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_AttendQueue = m_AttendQueue,
			m_TargetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_TargetElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_Durations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_Duration_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_HaveCoordinatedMeetings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_HaveCoordinatedMeetingData_RO_BufferLookup, ref base.CheckedStateRef),
			m_CalendarEventDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CalendarEventData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeetingArchetype = m_MeetingArchetype,
			m_JournalDataArchetype = m_JournalDataArchetype,
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.FindEventAttendantsSystem+Attend`  
- `Game.Simulation.FindEventAttendantsSystem+AttendJob`  
- `Game.Simulation.FindEventAttendantsSystem+ConsiderAttendanceJob`  
- `Game.Simulation.FindEventAttendantsSystem+TypeHandle`  

