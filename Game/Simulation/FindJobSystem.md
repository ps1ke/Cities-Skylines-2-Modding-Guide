# Game.Simulation.FindJobSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FindJobSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_JobSeekerQuery;
    private Unity.Entities.EntityQuery m_ResultsQuery;
    private Unity.Entities.EntityQuery m_FreeQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Collections.NativeArray<System.Int32> m_FreeCache;
    private Colossal.Collections.NativeValue<System.Int32> m_StartedWorking;
    private Unity.Jobs.JobHandle m_WriteDeps;
    private Game.Simulation.FindJobSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATE_INTERVAL;

    public FindJobSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_JobSeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_JobSeekerQuery;
```

- `private Unity.Entities.EntityQuery m_ResultsQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResultsQuery;
```

- `private Unity.Entities.EntityQuery m_FreeQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreeQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Collections.NativeArray<System.Int32> m_FreeCache`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_FreeCache;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_StartedWorking`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_StartedWorking;
```

- `private Unity.Jobs.JobHandle m_WriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_WriteDeps;
```

- `private Game.Simulation.FindJobSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FindJobSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATE_INTERVAL`  

```csharp
private static const System.Int32 UPDATE_INTERVAL;
```


## Constructors

- `public FindJobSystem()`  

```csharp
[Preserve]
	public FindJobSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CountHouseholdDataSystem = base.World.GetOrCreateSystemManaged<CountHouseholdDataSystem>();
		m_FreeQuery = GetEntityQuery(ComponentType.ReadOnly<FreeWorkplaces>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_StartedWorking = new NativeValue<int>(Allocator.Persistent);
		m_JobSeekerQuery = GetEntityQuery(ComponentType.ReadWrite<JobSeeker>(), ComponentType.ReadOnly<Owner>(), ComponentType.Exclude<PathInformation>(), ComponentType.Exclude<Deleted>());
		m_ResultsQuery = GetEntityQuery(ComponentType.ReadWrite<JobSeeker>(), ComponentType.ReadOnly<Owner>(), ComponentType.ReadOnly<PathInformation>(), ComponentType.Exclude<Deleted>());
		m_FreeCache = new NativeArray<int>(5, Allocator.Persistent);
		RequireAnyForUpdate(m_JobSeekerQuery, m_ResultsQuery);
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
		m_StartedWorking.Dispose();
		m_FreeCache.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_JobSeekerQuery.IsEmptyIgnoreFilter && !m_CountHouseholdDataSystem.IsCountDataNotReady())
		{
			JobHandle job = IJobExtensions.Schedule(new CalculateFreeWorkplaceJob
			{
				m_FreeWorkplaces = m_FreeQuery.ToComponentDataListAsync<FreeWorkplaces>(base.World.UpdateAllocator.ToAllocator, out job),
				m_FreeCache = m_FreeCache
			}, JobHandle.CombineDependencies(job, base.Dependency));
			FindJobJob jobData = new FindJobJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_JobSeekerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_JobSeeker_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CitizenDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Deleteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
				m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 80, 16).AsParallelWriter(),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_FreeCache = m_FreeCache,
				m_EmployableByEducation = m_CountHouseholdDataSystem.GetEmployables(),
				m_RandomSeed = RandomSeed.Next()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_JobSeekerQuery, JobHandle.CombineDependencies(job, base.Dependency));
			m_PathfindSetupSystem.AddQueueWriter(base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		}
		if (!m_ResultsQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			StartWorkingJob jobData2 = new StartWorkingJob
			{
				m_Chunks = m_ResultsQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_JobSeekerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_JobSeeker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PathInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EmployeeBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RW_BufferLookup, ref base.CheckedStateRef),
				m_FreeWorkplaces = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_FreeWorkplaces_RW_ComponentLookup, ref base.CheckedStateRef),
				m_WorkplaceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Deleteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WorkProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer(),
				m_SimulationFrame = m_SimulationSystem.frameIndex,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
				m_StartedWorking = m_StartedWorking
			};
			base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
			m_TriggerSystem.AddActionBufferWriter(base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
			m_WriteDeps = JobHandle.CombineDependencies(base.Dependency, m_WriteDeps);
		}
	}
```


## Nested types

- `Game.Simulation.FindJobSystem+CalculateFreeWorkplaceJob`  
- `Game.Simulation.FindJobSystem+FindJobJob`  
- `Game.Simulation.FindJobSystem+StartWorkingJob`  
- `Game.Simulation.FindJobSystem+TypeHandle`  

