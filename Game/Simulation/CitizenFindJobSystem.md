# Game.Simulation.CitizenFindJobSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenFindJobSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_UnemployedQuery;
    private Unity.Entities.EntityQuery m_EmployedQuery;
    private Unity.Entities.EntityQuery m_CitizenParametersQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CitizenFindJobSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kJobSeekCoolDownMax;
    public static readonly System.Int32 kJobSeekCoolDownMin;

    public CitizenFindJobSystem();

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

- `private Unity.Entities.EntityQuery m_UnemployedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnemployedQuery;
```

- `private Unity.Entities.EntityQuery m_EmployedQuery`  

```csharp
private Unity.Entities.EntityQuery m_EmployedQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenParametersQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CitizenFindJobSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CitizenFindJobSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kJobSeekCoolDownMax`  

```csharp
public static readonly System.Int32 kJobSeekCoolDownMax;
```

- `public static readonly System.Int32 kJobSeekCoolDownMin`  

```csharp
public static readonly System.Int32 kJobSeekCoolDownMin;
```


## Constructors

- `public CitizenFindJobSystem()`  

```csharp
[Preserve]
	public CitizenFindJobSystem()
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
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UnemployedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Citizen>(),
				ComponentType.ReadOnly<HouseholdMember>()
			},
			None = new ComponentType[7]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Worker>(),
				ComponentType.ReadOnly<Game.Citizens.Student>(),
				ComponentType.ReadOnly<HasJobSeeker>(),
				ComponentType.ReadOnly<HasSchoolSeeker>(),
				ComponentType.ReadOnly<HealthProblem>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_EmployedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Citizen>(),
				ComponentType.ReadOnly<HouseholdMember>(),
				ComponentType.ReadOnly<Worker>()
			},
			None = new ComponentType[6]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Game.Citizens.Student>(),
				ComponentType.ReadOnly<HasJobSeeker>(),
				ComponentType.ReadOnly<HasSchoolSeeker>(),
				ComponentType.ReadOnly<HealthProblem>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_CitizenParametersQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenParametersData>());
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CountWorkplacesSystem = base.World.GetOrCreateSystemManaged<CountWorkplacesSystem>();
		RequireForUpdate(m_CitizenParametersQuery);
		RequireForUpdate(m_UnemployedQuery);
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		CitizenFindJobJob jobData = new CitizenFindJobJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingAways = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_MovingAway_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HasJobSeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_HasJobSeeker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IsUnemployedFindJob = true,
			m_UpdateFrameIndex = updateFrame,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_RandomSeed = RandomSeed.Next(),
			m_AvailableWorkspacesByLevel = m_CountWorkplacesSystem.GetUnemployedWorkspaceByLevel(),
			m_SimulationFrame = m_SimulationSystem.frameIndex
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_UnemployedQuery, base.Dependency);
		if (!m_EmployedQuery.IsEmpty && RandomSeed.Next().GetRandom((int)m_SimulationSystem.frameIndex).NextFloat(1f) > m_CitizenParametersQuery.GetSingleton<CitizenParametersData>().m_SwitchJobRate)
		{
			CitizenFindJobJob jobData2 = new CitizenFindJobJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WorkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
				m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MovingAways = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_MovingAway_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HasJobSeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_HasJobSeeker_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IsUnemployedFindJob = false,
				m_UpdateFrameIndex = updateFrame,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_RandomSeed = RandomSeed.Next(),
				m_AvailableWorkspacesByLevel = m_CountWorkplacesSystem.GetFreeWorkplaces(),
				m_SimulationFrame = m_SimulationSystem.frameIndex
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_EmployedQuery, base.Dependency);
		}
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.CitizenFindJobSystem+CitizenFindJobJob`  
- `Game.Simulation.CitizenFindJobSystem+TypeHandle`  

