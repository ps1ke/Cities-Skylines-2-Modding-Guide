# Game.Simulation.ResourceAvailabilitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceAvailabilitySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityQuery m_WorkplaceGroup;
    private Unity.Entities.EntityQuery m_ServiceGroup;
    private Unity.Entities.EntityQuery m_RenterGroup;
    private Unity.Entities.EntityQuery m_ConvenienceFoodStoreGroup;
    private Unity.Entities.EntityQuery m_OutsideConnectionGroup;
    private Unity.Entities.EntityQuery m_AttractionGroup;
    private Unity.Entities.EntityQuery m_ResourceSellerGroup;
    private Unity.Entities.EntityQuery m_TaxiQuery;
    private Unity.Entities.EntityQuery m_BusStopQuery;
    private Unity.Entities.EntityQuery m_TramSubwayQuery;
    private Unity.Entities.EntityQuery m_ParkingLaneQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private Unity.Entities.Entity m_AvailabilityContainer;
    private Game.Net.AvailableResource m_LastQueriedResource;
    private Game.Net.AvailableResource m_LastWrittenResource;
    private Game.Net.AvailableResource <appliedResource>k__BackingField;
    private Game.Simulation.ResourceAvailabilitySystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public Game.Net.AvailableResource appliedResource { get; private set; }

    public ResourceAvailabilitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker, System.Single cost);
    private static System.Void AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker);
    private Unity.Jobs.JobHandle ApplyAvailability(Game.Net.AvailableResource resource, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle pathDeps);
    public System.Void Deserialize<TReader>(TReader reader);
    private Unity.Jobs.JobHandle FindLocations(Game.Net.AvailableResource resource, Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> pathTargets, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Unity.Jobs.JobHandle inputDeps);
    private Game.Pathfind.AvailabilityParameters GetAvailabilityParameters(Game.Net.AvailableResource resource, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> datas);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Unity.Entities.EntityQuery m_WorkplaceGroup`  

```csharp
private Unity.Entities.EntityQuery m_WorkplaceGroup;
```

- `private Unity.Entities.EntityQuery m_ServiceGroup`  

```csharp
private Unity.Entities.EntityQuery m_ServiceGroup;
```

- `private Unity.Entities.EntityQuery m_RenterGroup`  

```csharp
private Unity.Entities.EntityQuery m_RenterGroup;
```

- `private Unity.Entities.EntityQuery m_ConvenienceFoodStoreGroup`  

```csharp
private Unity.Entities.EntityQuery m_ConvenienceFoodStoreGroup;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionGroup`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionGroup;
```

- `private Unity.Entities.EntityQuery m_AttractionGroup`  

```csharp
private Unity.Entities.EntityQuery m_AttractionGroup;
```

- `private Unity.Entities.EntityQuery m_ResourceSellerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ResourceSellerGroup;
```

- `private Unity.Entities.EntityQuery m_TaxiQuery`  

```csharp
private Unity.Entities.EntityQuery m_TaxiQuery;
```

- `private Unity.Entities.EntityQuery m_BusStopQuery`  

```csharp
private Unity.Entities.EntityQuery m_BusStopQuery;
```

- `private Unity.Entities.EntityQuery m_TramSubwayQuery`  

```csharp
private Unity.Entities.EntityQuery m_TramSubwayQuery;
```

- `private Unity.Entities.EntityQuery m_ParkingLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkingLaneQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private Unity.Entities.Entity m_AvailabilityContainer`  

```csharp
private Unity.Entities.Entity m_AvailabilityContainer;
```

- `private Game.Net.AvailableResource m_LastQueriedResource`  

```csharp
private Game.Net.AvailableResource m_LastQueriedResource;
```

- `private Game.Net.AvailableResource m_LastWrittenResource`  

```csharp
private Game.Net.AvailableResource m_LastWrittenResource;
```

- `private Game.Net.AvailableResource <appliedResource>k__BackingField`  

```csharp
private Game.Net.AvailableResource <appliedResource>k__BackingField;
```

- `private Game.Simulation.ResourceAvailabilitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResourceAvailabilitySystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Properties

- `public Game.Net.AvailableResource appliedResource { get; private set }`  

```csharp
public Game.Net.AvailableResource appliedResource { get; private set; }
```


## Constructors

- `public ResourceAvailabilitySystem()`  

```csharp
[Preserve]
	public ResourceAvailabilitySystem()
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

- `private static AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker, System.Single cost) : System.Void`  

```csharp
private static void AddProvider(Entity provider, float capacity, UnsafeQueue<AvailabilityProvider>.ParallelWriter providers, ref PathfindTargetSeeker<PathfindTargetBuffer> targetSeeker)
	{
		if (targetSeeker.FindTargets(provider, 0f) != 0)
		{
			providers.Enqueue(new AvailabilityProvider(provider, capacity, 0f));
		}
	}
```

- `private static AddProvider(Unity.Entities.Entity provider, System.Single capacity, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Game.Pathfind.PathfindTargetSeeker`1[[Game.Pathfind.PathfindTargetBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker) : System.Void`  

```csharp
private static void AddProvider(Entity provider, float capacity, UnsafeQueue<AvailabilityProvider>.ParallelWriter providers, ref PathfindTargetSeeker<PathfindTargetBuffer> targetSeeker)
	{
		if (targetSeeker.FindTargets(provider, 0f) != 0)
		{
			providers.Enqueue(new AvailabilityProvider(provider, capacity, 0f));
		}
	}
```

- `private ApplyAvailability(Game.Net.AvailableResource resource, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle pathDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle ApplyAvailability(AvailableResource resource, JobHandle inputDeps, JobHandle pathDeps)
	{
		NativeArray<AvailabilityElement> availabilityElements = base.EntityManager.GetBuffer<AvailabilityElement>(m_AvailabilityContainer, isReadOnly: true).AsNativeArray();
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new ClearAvailabilityJob
		{
			m_ResourceType = resource,
			m_ResourceAvailabilityType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ResourceAvailability_RW_BufferTypeHandle, ref base.CheckedStateRef)
		}, m_EdgeGroup, inputDeps);
		if (resource == AvailableResource.Taxi)
		{
			TimeAction action = new TimeAction(Allocator.Persistent);
			NativeParallelHashSet<Entity> districts = new NativeParallelHashSet<Entity>(m_TaxiQuery.CalculateEntityCount(), Allocator.TempJob);
			FindTaxiDistrictsJob jobData = new FindTaxiDistrictsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TransportDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TransportDepot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TaxiType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Taxi_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransportDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_TransportDepot_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTransportDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceDistricts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_ServiceDistrict_RO_BufferLookup, ref base.CheckedStateRef),
				m_Districts = districts.AsParallelWriter()
			};
			ApplyTaxiAvailabilityJob jobData2 = new ApplyTaxiAvailabilityJob
			{
				m_AvailabilityElements = availabilityElements,
				m_Districts = districts,
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BorderDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_BorderDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceAvailability = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RW_BufferLookup, ref base.CheckedStateRef)
			};
			RefreshTaxiAvailabilityJob jobData3 = new RefreshTaxiAvailabilityJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_LaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathfindTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTransportData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ParkingLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ParkingLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TimeActions = action.m_TimeData.AsParallelWriter()
			};
			JobHandle jobHandle2 = IJobParallelForExtensions.Schedule(dependsOn: JobHandle.CombineDependencies(jobHandle, JobChunkExtensions.ScheduleParallel(jobData, m_TaxiQuery, inputDeps), pathDeps), jobData: jobData2, arrayLength: availabilityElements.Length, innerloopBatchCount: 4);
			JobHandle jobHandle3 = JobChunkExtensions.ScheduleParallel(jobData3, m_ParkingLaneQuery, jobHandle2);
			districts.Dispose(jobHandle2);
			m_PathfindQueueSystem.Enqueue(action, jobHandle3);
			return jobHandle3;
		}
		return IJobParallelForExtensions.Schedule(new ApplyAvailabilityJob
		{
			m_ResourceType = resource,
			m_AvailabilityElements = availabilityElements,
			m_ResourceAvailability = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RW_BufferLookup, ref base.CheckedStateRef)
		}, availabilityElements.Length, 16, jobHandle);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private FindLocations(Game.Net.AvailableResource resource, Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> pathTargets, Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> providers, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle FindLocations(AvailableResource resource, UnsafeQueue<PathTarget> pathTargets, UnsafeQueue<AvailabilityProvider> providers, JobHandle inputDeps)
	{
		m_TargetSeekerData.Update(this, m_AirwaySystem.GetAirwayData());
		PathfindParameters pathfindParameters = new PathfindParameters
		{
			m_MaxSpeed = 111.111115f,
			m_WalkSpeed = 5.555556f,
			m_Weights = new PathfindWeights(1f, 1f, 1f, 1f),
			m_Methods = PathMethod.Road,
			m_PathfindFlags = (PathfindFlags.Stable | PathfindFlags.IgnoreFlow | PathfindFlags.Simplified),
			m_IgnoredRules = (RuleFlags.HasBlockage | RuleFlags.ForbidCombustionEngines | RuleFlags.ForbidTransitTraffic | RuleFlags.ForbidHeavyTraffic | RuleFlags.ForbidSlowTraffic)
		};
		SetupQueueTarget setupQueueTarget = new SetupQueueTarget
		{
			m_Methods = PathMethod.Road,
			m_RoadTypes = RoadTypes.Car
		};
		switch (resource)
		{
		case AvailableResource.Workplaces:
			return JobChunkExtensions.ScheduleParallel(new FindWorkplaceLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_WorkProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter()
			}, m_WorkplaceGroup, inputDeps);
		case AvailableResource.Services:
			return JobChunkExtensions.ScheduleParallel(new FindServiceLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ServiceAvailableType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_ServiceAvailable_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter()
			}, m_ServiceGroup, inputDeps);
		case AvailableResource.UneducatedCitizens:
			return JobChunkExtensions.ScheduleParallel(new FindConsumerLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter(),
				m_Educated = false
			}, m_RenterGroup, inputDeps);
		case AvailableResource.EducatedCitizens:
			return JobChunkExtensions.ScheduleParallel(new FindConsumerLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter(),
				m_Educated = true
			}, m_RenterGroup, inputDeps);
		case AvailableResource.ConvenienceFoodStore:
			return JobChunkExtensions.ScheduleParallel(new FindConvenienceFoodStoreLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter()
			}, m_ConvenienceFoodStoreGroup, inputDeps);
		case AvailableResource.OutsideConnection:
			return JobChunkExtensions.ScheduleParallel(new FindOutsideConnectionLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter()
			}, m_OutsideConnectionGroup, inputDeps);
		case AvailableResource.GrainSupply:
		case AvailableResource.VegetableSupply:
		case AvailableResource.WoodSupply:
		case AvailableResource.TextilesSupply:
		case AvailableResource.ConvenienceFoodSupply:
		case AvailableResource.PaperSupply:
		case AvailableResource.VehiclesSupply:
		case AvailableResource.OilSupply:
		case AvailableResource.PetrochemicalsSupply:
		case AvailableResource.OreSupply:
		case AvailableResource.MetalsSupply:
		case AvailableResource.ElectronicsSupply:
		case AvailableResource.PlasticsSupply:
		case AvailableResource.CoalSupply:
		case AvailableResource.StoneSupply:
		case AvailableResource.LivestockSupply:
		case AvailableResource.CottonSupply:
		case AvailableResource.SteelSupply:
		case AvailableResource.MineralSupply:
		case AvailableResource.ChemicalSupply:
		case AvailableResource.MachinerySupply:
		case AvailableResource.BeveragesSupply:
		case AvailableResource.TimberSupply:
		case AvailableResource.FishSupply:
		{
			Resource resource2;
			switch (resource)
			{
			case AvailableResource.GrainSupply:
				resource2 = Resource.Grain;
				break;
			case AvailableResource.TextilesSupply:
				resource2 = Resource.Textiles;
				break;
			case AvailableResource.VegetableSupply:
				resource2 = Resource.Vegetables;
				break;
			case AvailableResource.WoodSupply:
				resource2 = Resource.Wood;
				break;
			case AvailableResource.ConvenienceFoodSupply:
				resource2 = Resource.ConvenienceFood;
				break;
			case AvailableResource.PaperSupply:
				resource2 = Resource.Paper;
				break;
			case AvailableResource.VehiclesSupply:
				resource2 = Resource.Vehicles;
				break;
			case AvailableResource.MetalsSupply:
				resource2 = Resource.Metals;
				break;
			case AvailableResource.OilSupply:
				resource2 = Resource.Oil;
				break;
			case AvailableResource.OreSupply:
				resource2 = Resource.Ore;
				break;
			case AvailableResource.PetrochemicalsSupply:
				resource2 = Resource.Petrochemicals;
				break;
			case AvailableResource.ElectronicsSupply:
				resource2 = Resource.Electronics;
				break;
			case AvailableResource.PlasticsSupply:
				resource2 = Resource.Plastics;
				break;
			case AvailableResource.CoalSupply:
				resource2 = Resource.Coal;
				break;
			case AvailableResource.StoneSupply:
				resource2 = Resource.Stone;
				break;
			case AvailableResource.LivestockSupply:
				resource2 = Resource.Livestock;
				break;
			case AvailableResource.CottonSupply:
				resource2 = Resource.Cotton;
				break;
			case AvailableResource.SteelSupply:
				resource2 = Resource.Steel;
				break;
			case AvailableResource.MineralSupply:
				resource2 = Resource.Minerals;
				break;
			case AvailableResource.ChemicalSupply:
				resource2 = Resource.Chemicals;
				break;
			case AvailableResource.TimberSupply:
				resource2 = Resource.Timber;
				break;
			case AvailableResource.MachinerySupply:
				resource2 = Resource.Machinery;
				break;
			case AvailableResource.BeveragesSupply:
				resource2 = Resource.Beverages;
				break;
			case AvailableResource.FishSupply:
				resource2 = Resource.Fish;
				break;
			default:
				return inputDeps;
			}
			return JobChunkExtensions.ScheduleParallel(new FindSellerLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter(),
				m_Resource = resource2,
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ProcessData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StorageCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StorageDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TradeCosts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_TradeCost_RO_BufferLookup, ref base.CheckedStateRef)
			}, m_ResourceSellerGroup, inputDeps);
		}
		case AvailableResource.Attractiveness:
			return JobChunkExtensions.ScheduleParallel(new FindAttractionLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_AttractivenessProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_AttractivenessProvider_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter()
			}, m_AttractionGroup, inputDeps);
		case AvailableResource.Taxi:
			return JobChunkExtensions.ScheduleParallel(new FindTaxiLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TransportDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TransportDepot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TaxiType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Taxi_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TransportDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_TransportDepot_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTransportDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter()
			}, m_TaxiQuery, inputDeps);
		case AvailableResource.Bus:
			return JobChunkExtensions.ScheduleParallel(new FindBusStopLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter()
			}, m_BusStopQuery, inputDeps);
		case AvailableResource.TramSubway:
			return JobChunkExtensions.ScheduleParallel(new FindTramSubwayLocationsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_SubWayStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_SubwayStop_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, pathTargets.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true),
				m_Providers = providers.AsParallelWriter()
			}, m_TramSubwayQuery, inputDeps);
		default:
			return inputDeps;
		}
	}
```

- `private GetAvailabilityParameters(Game.Net.AvailableResource resource, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> datas) : Game.Pathfind.AvailabilityParameters`  

```csharp
private AvailabilityParameters GetAvailabilityParameters(AvailableResource resource, ResourcePrefabs prefabs, ComponentLookup<ResourceData> datas)
	{
		switch (resource)
		{
		case AvailableResource.GrainSupply:
		case AvailableResource.VegetableSupply:
		case AvailableResource.WoodSupply:
		case AvailableResource.TextilesSupply:
		case AvailableResource.ConvenienceFoodSupply:
		case AvailableResource.PaperSupply:
		case AvailableResource.VehiclesSupply:
		case AvailableResource.OilSupply:
		case AvailableResource.PetrochemicalsSupply:
		case AvailableResource.OreSupply:
		case AvailableResource.MetalsSupply:
		case AvailableResource.ElectronicsSupply:
		case AvailableResource.PlasticsSupply:
		case AvailableResource.CoalSupply:
		case AvailableResource.StoneSupply:
		case AvailableResource.LivestockSupply:
		case AvailableResource.CottonSupply:
		case AvailableResource.SteelSupply:
		case AvailableResource.MineralSupply:
		case AvailableResource.ChemicalSupply:
		case AvailableResource.MachinerySupply:
		case AvailableResource.BeveragesSupply:
		case AvailableResource.TimberSupply:
		{
			Resource resource2 = EconomyUtils.GetResource(resource);
			float costFactor = 0.1f;
			if (resource2 != Resource.NoResource)
			{
				costFactor = 0.1f * EconomyUtils.GetTransportCost(1f, 0, EconomyUtils.GetWeight(resource2, prefabs, ref datas), StorageTransferFlags.Car);
			}
			return new AvailabilityParameters
			{
				m_DensityWeight = 0.05f,
				m_CostFactor = costFactor,
				m_ResultFactor = 0.01f
			};
		}
		case AvailableResource.Workplaces:
			return new AvailabilityParameters
			{
				m_DensityWeight = 0.05f,
				m_CostFactor = 0.1f,
				m_ResultFactor = 0.08f
			};
		case AvailableResource.UneducatedCitizens:
		case AvailableResource.EducatedCitizens:
			return new AvailabilityParameters
			{
				m_DensityWeight = 0.05f,
				m_CostFactor = 0.5f,
				m_ResultFactor = 1f
			};
		case AvailableResource.Services:
		case AvailableResource.ConvenienceFoodStore:
		case AvailableResource.Attractiveness:
			return new AvailabilityParameters
			{
				m_DensityWeight = 0.05f,
				m_CostFactor = 0.1f,
				m_ResultFactor = 1f
			};
		case AvailableResource.OutsideConnection:
			return new AvailabilityParameters
			{
				m_DensityWeight = 0.05f,
				m_CostFactor = 0.1f,
				m_ResultFactor = 3f
			};
		case AvailableResource.Taxi:
			return new AvailabilityParameters
			{
				m_DensityWeight = 0.1f,
				m_CostFactor = 0.05f,
				m_ResultFactor = 1f
			};
		case AvailableResource.Bus:
			return new AvailabilityParameters
			{
				m_DensityWeight = 0.05f,
				m_CostFactor = 0.1f,
				m_ResultFactor = 1f
			};
		case AvailableResource.TramSubway:
			return new AvailabilityParameters
			{
				m_DensityWeight = 0.05f,
				m_CostFactor = 0.1f,
				m_ResultFactor = 1f
			};
		default:
			return new AvailabilityParameters
			{
				m_DensityWeight = 1f,
				m_CostFactor = 1f,
				m_ResultFactor = 1f
			};
		}
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 64;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_AirwaySystem = base.World.GetOrCreateSystemManaged<AirwaySystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_EdgeGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Net.Edge>(), ComponentType.ReadWrite<ResourceAvailability>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_WorkplaceGroup = GetEntityQuery(ComponentType.ReadOnly<WorkProvider>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Game.Objects.OutsideConnection>());
		m_ServiceGroup = GetEntityQuery(ComponentType.ReadOnly<ServiceAvailable>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_RenterGroup = GetEntityQuery(ComponentType.ReadOnly<ResidentialProperty>(), ComponentType.ReadOnly<Renter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ConvenienceFoodStoreGroup = GetEntityQuery(ComponentType.ReadOnly<ServiceAvailable>(), ComponentType.ReadOnly<ResourceSeller>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_OutsideConnectionGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Objects.ElectricityOutsideConnection>(), ComponentType.Exclude<Game.Objects.WaterPipeOutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_AttractionGroup = GetEntityQuery(ComponentType.ReadOnly<AttractivenessProvider>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ResourceSellerGroup = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<ResourceSeller>(),
				ComponentType.ReadOnly<Game.Companies.StorageCompany>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<ServiceAvailable>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_TaxiQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<ServiceDispatch>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.TransportDepot>(),
				ComponentType.ReadOnly<Game.Vehicles.Taxi>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_BusStopQuery = GetEntityQuery(ComponentType.ReadOnly<BusStop>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_TramSubwayQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Routes.TransportStop>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<TramStop>(),
				ComponentType.ReadOnly<SubwayStop>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_ParkingLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.ParkingLane>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_TargetSeekerData = new PathfindTargetSeekerData(this);
		m_AvailabilityContainer = base.EntityManager.CreateEntity(ComponentType.ReadWrite<AvailabilityElement>());
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
		if (m_LastQueriedResource != AvailableResource.Count)
		{
			m_LastWrittenResource = m_LastQueriedResource;
			appliedResource = m_LastWrittenResource;
		}
		else
		{
			m_LastQueriedResource = m_LastWrittenResource;
			m_LastWrittenResource = AvailableResource.Count;
		}
		if (++m_LastQueriedResource == AvailableResource.Count)
		{
			m_LastQueriedResource = AvailableResource.Workplaces;
		}
		AvailabilityAction action = new AvailabilityAction(Allocator.Persistent, GetAvailabilityParameters(m_LastQueriedResource, m_ResourceSystem.GetPrefabs(), GetComponentLookup<ResourceData>(isReadOnly: true)));
		JobHandle jobHandle = FindLocations(m_LastQueriedResource, action.data.m_Sources, action.data.m_Providers, base.Dependency);
		if (m_LastWrittenResource != AvailableResource.Count)
		{
			JobHandle job = ApplyAvailability(m_LastWrittenResource, base.Dependency, jobHandle);
			base.Dependency = JobHandle.CombineDependencies(job, jobHandle);
		}
		else
		{
			base.Dependency = jobHandle;
		}
		m_PathfindQueueSystem.Enqueue(action, m_AvailabilityContainer, jobHandle, m_SimulationSystem.frameIndex + 64, this);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_LastQueriedResource = AvailableResource.Count;
		m_LastWrittenResource = AvailableResource.FishSupply;
		appliedResource = AvailableResource.Count;
	}
```


## Nested types

- `Game.Simulation.ResourceAvailabilitySystem+FindWorkplaceLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindAttractionLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindServiceLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindConsumerLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindConvenienceFoodStoreLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindOutsideConnectionLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindSellerLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindTaxiLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindBusStopLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindTramSubwayLocationsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+ClearAvailabilityJob`  
- `Game.Simulation.ResourceAvailabilitySystem+ApplyAvailabilityJob`  
- `Game.Simulation.ResourceAvailabilitySystem+FindTaxiDistrictsJob`  
- `Game.Simulation.ResourceAvailabilitySystem+ApplyTaxiAvailabilityJob`  
- `Game.Simulation.ResourceAvailabilitySystem+RefreshTaxiAvailabilityJob`  
- `Game.Simulation.ResourceAvailabilitySystem+TypeHandle`  

