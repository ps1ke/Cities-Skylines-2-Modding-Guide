# Game.Simulation.WaitingPassengersSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaitingPassengersSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_StopQuery;
    private Unity.Entities.EntityQuery m_ResidentQuery;
    private Game.Simulation.WaitingPassengersSystem+TypeHandle __TypeHandle;

    public WaitingPassengersSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_StopQuery`  

```csharp
private Unity.Entities.EntityQuery m_StopQuery;
```

- `private Unity.Entities.EntityQuery m_ResidentQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentQuery;
```

- `private Game.Simulation.WaitingPassengersSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaitingPassengersSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaitingPassengersSystem()`  

```csharp
[Preserve]
	public WaitingPassengersSystem()
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
		return 256;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetExistingSystemManaged<EndFrameBarrier>();
		m_StopQuery = GetEntityQuery(ComponentType.ReadWrite<WaitingPassengers>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ResidentQuery = GetEntityQuery(ComponentType.ReadOnly<HumanCurrentLane>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<GroupMember>());
		RequireForUpdate(m_StopQuery);
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
		ClearWaitingPassengersJob jobData = new ClearWaitingPassengersJob
		{
			m_WaitingPassengersType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_WaitingPassengers_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		CountWaitingPassengersJob jobData2 = new CountWaitingPassengersJob
		{
			m_HumanCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResidentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_GroupCreatureType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Creatures_GroupCreature_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_QueueType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Creatures_Queue_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_WaitingPassengersData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_WaitingPassengers_RW_ComponentLookup, ref base.CheckedStateRef)
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new TickWaitingPassengersJob
		{
			m_RandomSeed = RandomSeed.Next(),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_WaitingPassengersType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_WaitingPassengers_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, dependsOn: JobChunkExtensions.ScheduleParallel(dependsOn: JobChunkExtensions.ScheduleParallel(jobData, m_StopQuery, base.Dependency), jobData: jobData2, query: m_ResidentQuery), query: m_StopQuery);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.WaitingPassengersSystem+ClearWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+CountWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+TickWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+TypeHandle`  

