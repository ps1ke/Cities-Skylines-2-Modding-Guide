# Game.Citizens.MeetingInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeetingInitializeSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier5;
    private Unity.Entities.EntityQuery m_MeetingQuery;
    private Game.Citizens.MeetingInitializeSystem+TypeHandle __TypeHandle;

    public MeetingInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier5`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier5;
```

- `private Unity.Entities.EntityQuery m_MeetingQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeetingQuery;
```

- `private Game.Citizens.MeetingInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.MeetingInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MeetingInitializeSystem()`  

```csharp
[Preserve]
	public MeetingInitializeSystem()
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
		m_ModificationBarrier5 = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_MeetingQuery = GetEntityQuery(ComponentType.ReadOnly<CoordinatedMeeting>(), ComponentType.ReadWrite<CoordinatedMeetingAttendee>(), ComponentType.ReadOnly<Created>());
		RequireForUpdate(m_MeetingQuery);
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
		InitializeMeetingJob jobData = new InitializeMeetingJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_AttendeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_CoordinatedMeetingAttendee_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_Attendings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_AttendingMeeting_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier5.CreateCommandBuffer()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_MeetingQuery, base.Dependency);
		m_ModificationBarrier5.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Citizens.MeetingInitializeSystem+InitializeMeetingJob`  
- `Game.Citizens.MeetingInitializeSystem+TypeHandle`  

