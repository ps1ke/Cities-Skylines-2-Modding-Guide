# Game.Vehicles.ReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ReferencesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Entities.EntityQuery m_CarQuery;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityQuery m_LayoutQuery;
    private Game.Vehicles.ReferencesSystem+TypeHandle __TypeHandle;

    public ReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Unity.Entities.EntityQuery m_CarQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarQuery;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.EntityQuery m_LayoutQuery`  

```csharp
private Unity.Entities.EntityQuery m_LayoutQuery;
```

- `private Game.Vehicles.ReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Vehicles.ReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ReferencesSystem()`  

```csharp
[Preserve]
	public ReferencesSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_CarQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<Vehicle>(), ComponentType.ReadWrite<CarCurrentLane>(), ComponentType.Exclude<Temp>());
		m_VehicleQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Vehicle>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_LayoutQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<LayoutElement>(),
				ComponentType.ReadOnly<Controller>()
			}
		});
		RequireAnyForUpdate(m_CarQuery, m_VehicleQuery, m_LayoutQuery);
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
		JobHandle jobHandle = default(JobHandle);
		if (!m_CarQuery.IsEmptyIgnoreFilter)
		{
			jobHandle = JobChunkExtensions.ScheduleParallel(new InitializeCurrentLaneJob
			{
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef)
			}, m_CarQuery, base.Dependency);
		}
		JobHandle job = default(JobHandle);
		if (!m_LayoutQuery.IsEmptyIgnoreFilter)
		{
			job = JobChunkExtensions.Schedule(new UpdateLayoutReferencesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Layouts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RW_BufferLookup, ref base.CheckedStateRef)
			}, m_LayoutQuery, base.Dependency);
		}
		JobHandle jobHandle2 = default(JobHandle);
		if (!m_VehicleQuery.IsEmptyIgnoreFilter)
		{
			jobHandle2 = JobChunkExtensions.Schedule(new UpdateVehicleReferencesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PersonalCarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeliveryTruckType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarTrailerLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarTrailerLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WatercraftCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AircraftCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TrainCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ParkedCarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ParkedTrainType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MovingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OdometerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Odometer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentRouteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_CurrentRoute_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BlockedLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_BlockedLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_GarageLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_GarageLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PublicTransportVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PublicTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CargoTransportVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CargoTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TaxiData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TaxiData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_CarKeepers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RW_ComponentLookup, ref base.CheckedStateRef),
				m_TransportDepots = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_TransportDepot_RW_ComponentLookup, ref base.CheckedStateRef),
				m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RW_BufferLookup, ref base.CheckedStateRef),
				m_GuestVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_GuestVehicle_RW_BufferLookup, ref base.CheckedStateRef),
				m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RW_BufferLookup, ref base.CheckedStateRef),
				m_RouteVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RW_BufferLookup, ref base.CheckedStateRef),
				m_SearchTree = m_SearchSystem.GetMovingSearchTree(readOnly: false, out var dependencies),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
			}, m_VehicleQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle, dependencies));
			m_SearchSystem.AddMovingSearchTreeWriter(jobHandle2);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		}
		base.Dependency = JobHandle.CombineDependencies(jobHandle, job, jobHandle2);
	}
```


## Nested types

- `Game.Vehicles.ReferencesSystem+InitializeCurrentLaneJob`  
- `Game.Vehicles.ReferencesSystem+UpdateLayoutReferencesJob`  
- `Game.Vehicles.ReferencesSystem+UpdateVehicleReferencesJob`  
- `Game.Vehicles.ReferencesSystem+TypeHandle`  

