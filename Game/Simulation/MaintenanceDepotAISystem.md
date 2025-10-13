# Game.Simulation.MaintenanceDepotAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MaintenanceDepotAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData;
    private Game.Simulation.MaintenanceDepotAISystem+TypeHandle __TypeHandle;

    public MaintenanceDepotAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData`  

```csharp
private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData;
```

- `private Game.Simulation.MaintenanceDepotAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.MaintenanceDepotAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MaintenanceDepotAISystem()`  

```csharp
[Preserve]
	public MaintenanceDepotAISystem()
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

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 160;
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
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_MaintenanceVehicleSelectData = new MaintenanceVehicleSelectData(this);
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.MaintenanceDepot>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_VehiclePrefabQuery = GetEntityQuery(MaintenanceVehicleSelectData.GetEntityQueryDesc());
		m_MaintenanceRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<MaintenanceRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_HandleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<HandleRequest>(), ComponentType.ReadWrite<Event>());
		m_ParkedToMovingRemoveTypes = new ComponentTypeSet(ComponentType.ReadWrite<ParkedCar>(), ComponentType.ReadWrite<Stopped>());
		m_ParkedToMovingCarAddTypes = new ComponentTypeSet(new ComponentType[14]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<CarNavigation>(),
			ComponentType.ReadWrite<CarNavigationLane>(),
			ComponentType.ReadWrite<CarCurrentLane>(),
			ComponentType.ReadWrite<PathOwner>(),
			ComponentType.ReadWrite<Target>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<PathElement>(),
			ComponentType.ReadWrite<PathInformation>(),
			ComponentType.ReadWrite<ServiceDispatch>(),
			ComponentType.ReadWrite<Swaying>(),
			ComponentType.ReadWrite<Updated>()
		});
		RequireForUpdate(m_BuildingQuery);
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
		m_MaintenanceVehicleSelectData.PreUpdate(this, m_CityConfigurationSystem, m_VehiclePrefabQuery, Allocator.TempJob, out var jobHandle);
		NativeQueue<MaintenanceDepotAction> actionQueue = new NativeQueue<MaintenanceDepotAction>(Allocator.TempJob);
		MaintenanceDepotTickJob jobData = new MaintenanceDepotTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnedVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_MaintenanceDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_MaintenanceDepot_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceRequestType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_MaintenanceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_MaintenanceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ServiceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SurfaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Surface_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MaintenanceVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_MaintenanceVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetConditionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NetCondition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabMaintenanceDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MaintenanceDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_SimulationFrameIndex = m_SimulationSystem.frameIndex,
			m_MaintenanceRequestArchetype = m_MaintenanceRequestArchetype,
			m_HandleRequestArchetype = m_HandleRequestArchetype,
			m_ParkedToMovingRemoveTypes = m_ParkedToMovingRemoveTypes,
			m_ParkedToMovingCarAddTypes = m_ParkedToMovingCarAddTypes,
			m_MaintenanceVehicleSelectData = m_MaintenanceVehicleSelectData,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_ActionQueue = actionQueue.AsParallelWriter()
		};
		MaintenanceDepotActionJob jobData2 = new MaintenanceDepotActionJob
		{
			m_MaintenanceVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_MaintenanceVehicle_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ActionQueue = actionQueue
		};
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData, m_BuildingQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle));
		JobHandle jobHandle3 = IJobExtensions.Schedule(jobData2, jobHandle2);
		actionQueue.Dispose(jobHandle3);
		m_MaintenanceVehicleSelectData.PostUpdate(jobHandle2);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = jobHandle3;
	}
```


## Nested types

- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotAction`  
- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotTickJob`  
- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotActionJob`  
- `Game.Simulation.MaintenanceDepotAISystem+TypeHandle`  

