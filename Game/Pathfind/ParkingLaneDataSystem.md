# Game.Pathfind.ParkingLaneDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkingLaneDataSystem : Game.GameSystemBase
{
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Game.Pathfind.ParkingLaneDataSystem+TypeHandle __TypeHandle;

    public ParkingLaneDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Game.Pathfind.ParkingLaneDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.ParkingLaneDataSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ParkingLaneDataSystem()`  

```csharp
[Preserve]
	public ParkingLaneDataSystem()
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
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_LaneQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<GarageLane>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PathfindUpdated>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<GarageLane>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		RequireForUpdate(m_LaneQuery);
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
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateLaneDataJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneOverlapType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ParkingLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ParkingLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectionLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ConnectionLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GarageLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_GarageLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnLocationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_SpawnLocation_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LaneObject_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BorderDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_BorderDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_District_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ParkingFacility_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_City_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnspawnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabParkingFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingPropertyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWorkplaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_BuildingModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_BuildingModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_ActivityLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_MovingObjectSearchTree = m_ObjectSearchSystem.GetMovingSearchTree(readOnly: true, out dependencies)
		}, m_LaneQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_ObjectSearchSystem.AddMovingSearchTreeReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Pathfind.ParkingLaneDataSystem+UpdateLaneDataJob`  
- `Game.Pathfind.ParkingLaneDataSystem+TypeHandle`  

