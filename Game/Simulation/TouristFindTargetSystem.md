# Game.Simulation.TouristFindTargetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TouristFindTargetSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_SeekerQuery;
    private Unity.Entities.ComponentTypeSet m_PathfindTypes;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Events.AddMeetingSystem m_AddMeetingSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.TouristFindTargetSystem+HotelReserveAction> m_HotelReserveQueue;
    private Game.Simulation.TouristFindTargetSystem+TypeHandle __TypeHandle;

    public TouristFindTargetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_SeekerQuery;
```

- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_PathfindTypes;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Events.AddMeetingSystem m_AddMeetingSystem`  

```csharp
private Game.Events.AddMeetingSystem m_AddMeetingSystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.TouristFindTargetSystem+HotelReserveAction> m_HotelReserveQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.TouristFindTargetSystem+HotelReserveAction> m_HotelReserveQueue;
```

- `private Game.Simulation.TouristFindTargetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TouristFindTargetSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TouristFindTargetSystem()`  

```csharp
[Preserve]
	public TouristFindTargetSystem()
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
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_AddMeetingSystem = base.World.GetOrCreateSystemManaged<AddMeetingSystem>();
		m_SeekerQuery = GetEntityQuery(ComponentType.ReadWrite<TouristHousehold>(), ComponentType.ReadWrite<LodgingSeeker>(), ComponentType.Exclude<MovingAway>(), ComponentType.Exclude<Target>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_PathfindTypes = new ComponentTypeSet(ComponentType.ReadWrite<PathInformation>());
		m_HotelReserveQueue = new NativeQueue<HotelReserveAction>(Allocator.Persistent);
		RequireForUpdate(m_SeekerQuery);
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
		m_HotelReserveQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle deps;
		TouristFindTargetJob jobData = new TouristFindTargetJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RenterBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizenBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_OwnedVehicleBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_PathfindTypeSet = m_PathfindTypes,
			m_PathInformations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LodgingProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_LodgingProvider_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 64).AsParallelWriter(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_MeetingQueue = m_AddMeetingSystem.GetMeetingQueue(out deps).AsParallelWriter(),
			m_ReserveQueue = m_HotelReserveQueue.AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_SeekerQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		m_PathfindSetupSystem.AddQueueWriter(base.Dependency);
		HotelReserveJob jobData2 = new HotelReserveJob
		{
			m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RW_ComponentLookup, ref base.CheckedStateRef),
			m_LodgingProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_LodgingProvider_RW_ComponentLookup, ref base.CheckedStateRef),
			m_RenterBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RW_BufferLookup, ref base.CheckedStateRef),
			m_ReserveQueue = m_HotelReserveQueue,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.TouristFindTargetSystem+HotelReserveAction`  
- `Game.Simulation.TouristFindTargetSystem+TouristFindTargetJob`  
- `Game.Simulation.TouristFindTargetSystem+HotelReserveJob`  
- `Game.Simulation.TouristFindTargetSystem+TypeHandle`  

