# Game.Simulation.MeetingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeetingSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_MeetingGroup;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.MeetingSystem+TypeHandle __TypeHandle;

    public MeetingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_MeetingGroup`  

```csharp
private Unity.Entities.EntityQuery m_MeetingGroup;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.MeetingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.MeetingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MeetingSystem()`  

```csharp
[Preserve]
	public MeetingSystem()
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
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_MeetingGroup = GetEntityQuery(ComponentType.ReadWrite<CoordinatedMeeting>(), ComponentType.ReadWrite<CoordinatedMeetingAttendee>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_MeetingGroup);
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
		MeetingJob jobData = new MeetingJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_AttendeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_CoordinatedMeetingAttendee_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_MeetingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CoordinatedMeeting_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeetingDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_HaveCoordinatedMeetingData_RO_BufferLookup, ref base.CheckedStateRef),
			m_AttendingMeetings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_AttendingMeeting_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CalendarEvents = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CalendarEventData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_MeetingGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.MeetingSystem+MeetingJob`  
- `Game.Simulation.MeetingSystem+TypeHandle`  

