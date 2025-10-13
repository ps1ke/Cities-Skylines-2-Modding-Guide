# Game.Simulation.LeisureSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LeisureSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PathfindSetupSystem m_PathFindSetupSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Events.AddMeetingSystem m_AddMeetingSystem;
    private Unity.Entities.EntityQuery m_LeisureQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_LeisureParameterQuery;
    private Unity.Entities.EntityQuery m_ResidentPrefabQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Unity.Entities.ComponentTypeSet m_PathfindTypes;
    private Unity.Collections.NativeQueue<Game.Simulation.LeisureEvent> m_LeisureQueue;
    private Game.Simulation.LeisureSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kLeisureConsumeAmount;

    public LeisureSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> tempProviderList, Game.Prefabs.LeisureProviderData providerToAdd);
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

- `private Game.Simulation.PathfindSetupSystem m_PathFindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathFindSetupSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Events.AddMeetingSystem m_AddMeetingSystem`  

```csharp
private Game.Events.AddMeetingSystem m_AddMeetingSystem;
```

- `private Unity.Entities.EntityQuery m_LeisureQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LeisureParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ResidentPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_PathfindTypes;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.LeisureEvent> m_LeisureQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.LeisureEvent> m_LeisureQueue;
```

- `private Game.Simulation.LeisureSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LeisureSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kLeisureConsumeAmount`  

```csharp
private static readonly System.Int32 kLeisureConsumeAmount;
```


## Constructors

- `public LeisureSystem()`  

```csharp
[Preserve]
	public LeisureSystem()
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

- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> tempProviderList, Game.Prefabs.LeisureProviderData providerToAdd) : System.Void`  

```csharp
public static void AddToTempList(NativeList<LeisureProviderData> tempProviderList, LeisureProviderData providerToAdd)
	{
		for (int i = 0; i < tempProviderList.Length; i++)
		{
			LeisureProviderData value = tempProviderList[i];
			if (value.m_LeisureType == providerToAdd.m_LeisureType && value.m_Resources == providerToAdd.m_Resources)
			{
				value.m_Efficiency += providerToAdd.m_Efficiency;
				tempProviderList[i] = value;
				return;
			}
		}
		tempProviderList.Add(in providerToAdd);
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
		m_PathFindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_AddMeetingSystem = base.World.GetOrCreateSystemManaged<AddMeetingSystem>();
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_LeisureParameterQuery = GetEntityQuery(ComponentType.ReadOnly<LeisureParametersData>());
		m_LeisureQuery = GetEntityQuery(ComponentType.ReadWrite<Citizen>(), ComponentType.ReadWrite<Leisure>(), ComponentType.ReadWrite<TripNeeded>(), ComponentType.ReadWrite<CurrentBuilding>(), ComponentType.Exclude<HealthProblem>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ResidentPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ObjectData>(), ComponentType.ReadOnly<HumanData>(), ComponentType.ReadOnly<ResidentData>(), ComponentType.ReadOnly<PrefabData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_PopulationQuery = GetEntityQuery(ComponentType.ReadOnly<Population>());
		m_PathfindTypes = new ComponentTypeSet(ComponentType.ReadWrite<PathInformation>(), ComponentType.ReadWrite<PathElement>());
		m_LeisureQueue = new NativeQueue<LeisureEvent>(Allocator.Persistent);
		RequireForUpdate(m_LeisureQuery);
		RequireForUpdate(m_EconomyParameterQuery);
		RequireForUpdate(m_LeisureParameterQuery);
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
		m_LeisureQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		float value = m_ClimateSystem.precipitation.value;
		JobHandle outJobHandle;
		JobHandle deps;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new LeisureJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_LeisureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Leisure_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_TripType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_CreatureDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CreatureData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResidentDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ResidentData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInfos = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarKeepers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PersonalCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Targets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LeisureProviderDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LeisureProviderData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_CitizenDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Renters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabHumanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HumanData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Purposes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IndustrialProcesses = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceAvailables = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceAvailable_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PopulationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_RenterBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConsumptionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_TimeOfDay = m_TimeSystem.normalizedTime,
			m_UpdateFrameIndex = updateFrameWithInterval,
			m_Weather = value,
			m_Temperature = m_ClimateSystem.temperature,
			m_RandomSeed = RandomSeed.Next(),
			m_PathfindTypes = m_PathfindTypes,
			m_HumanChunks = m_ResidentPrefabQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_PathfindQueue = m_PathFindSetupSystem.GetQueue(this, 64).AsParallelWriter(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_MeetingQueue = m_AddMeetingSystem.GetMeetingQueue(out deps).AsParallelWriter(),
			m_LeisureQueue = m_LeisureQueue.AsParallelWriter(),
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_PopulationEntity = m_PopulationQuery.GetSingletonEntity()
		}, m_LeisureQuery, JobHandle.CombineDependencies(base.Dependency, JobHandle.CombineDependencies(outJobHandle, deps)));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		m_PathFindSetupSystem.AddQueueWriter(jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new SpendLeisurejob
		{
			m_ServiceAvailables = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceAvailable_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RW_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IndustrialProcesses = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_LeisureQueue = m_LeisureQueue
		}, jobHandle);
		m_ResourceSystem.AddPrefabsReader(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.LeisureSystem+SpendLeisurejob`  
- `Game.Simulation.LeisureSystem+LeisureJob`  
- `Game.Simulation.LeisureSystem+TypeHandle`  

