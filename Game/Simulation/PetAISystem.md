# Game.Simulation.PetAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PetAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Unity.Entities.ComponentTypeSet m_CurrentLaneTypes;
    private Game.Simulation.PetAISystem+TypeHandle __TypeHandle;

    public PetAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentLaneTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentLaneTypes;
```

- `private Game.Simulation.PetAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PetAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PetAISystem()`  

```csharp
[Preserve]
	public PetAISystem()
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

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 5;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_CreatureQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Creatures.Pet>(), ComponentType.ReadOnly<Animal>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<Target>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Stumbling>());
		m_ResetTripArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<ResetTrip>());
		m_CurrentLaneTypes = new ComponentTypeSet(new ComponentType[6]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<AnimalNavigation>(),
			ComponentType.ReadWrite<AnimalCurrentLane>(),
			ComponentType.ReadWrite<Blocker>()
		});
		RequireForUpdate(m_CreatureQuery);
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
		NativeQueue<Boarding> boardingQueue = new NativeQueue<Boarding>(Allocator.TempJob);
		PetTickJob jobData = new PetTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CurrentVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GroupMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GroupCreatureType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Creatures_GroupCreature_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_AnimalType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Animal_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Pet_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Creature_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnspawnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OnFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PersonalCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxiData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Taxi_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PoliceCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PoliceCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathOwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathOwner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabActivityLocationElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_LefthandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_ResetTripArchetype = m_ResetTripArchetype,
			m_BoardingQueue = boardingQueue.AsParallelWriter(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		JobHandle dependencies;
		BoardingJob jobData2 = new BoardingJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Creatures = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Creature_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Passengers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_Passenger_RW_BufferLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RW_BufferLookup, ref base.CheckedStateRef),
			m_CurrentLaneTypes = m_CurrentLaneTypes,
			m_BoardingQueue = boardingQueue,
			m_SearchTree = m_ObjectSearchSystem.GetMovingSearchTree(readOnly: false, out dependencies),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
		};
		JobHandle job = JobChunkExtensions.ScheduleParallel(jobData, m_CreatureQuery, base.Dependency);
		JobHandle jobHandle = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(job, dependencies));
		boardingQueue.Dispose(jobHandle);
		m_ObjectSearchSystem.AddMovingSearchTreeWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.PetAISystem+Boarding`  
- `Game.Simulation.PetAISystem+BoardingType`  
- `Game.Simulation.PetAISystem+PetTickJob`  
- `Game.Simulation.PetAISystem+BoardingJob`  
- `Game.Simulation.PetAISystem+TypeHandle`  

