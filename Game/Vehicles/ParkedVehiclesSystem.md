# Game.Vehicles.ParkedVehiclesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkedVehiclesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_DeletedVehicleQuery;
    private Unity.Entities.EntityQuery m_PoliceCarQuery;
    private Unity.Entities.EntityQuery m_FireEngineQuery;
    private Unity.Entities.EntityQuery m_HealthcareVehicleQuery;
    private Unity.Entities.EntityQuery m_TransportVehicleQuery;
    private Unity.Entities.EntityQuery m_PostVanQuery;
    private Unity.Entities.EntityQuery m_MaintenanceVehicleQuery;
    private Unity.Entities.EntityQuery m_GarbageTruckQuery;
    private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData;
    private Game.Prefabs.FireEngineSelectData m_FireEngineSelectData;
    private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData;
    private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
    private Game.Prefabs.PostVanSelectData m_PostVanSelectData;
    private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData;
    private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData;
    private Game.Vehicles.ParkedVehiclesSystem+TypeHandle __TypeHandle;

    public ParkedVehiclesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CollectDeletedVehicles(Unity.Collections.NativeParallelMultiHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deletedVehicleMap, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void DuplicateVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private static Unity.Entities.Entity FindDeletedVehicle(Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Objects.Transform transform, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedMap);
    private System.Void FindParkingLocations(Unity.Entities.Entity entity, Unity.Collections.NativeList`1[[Game.Vehicles.ParkedVehiclesSystem+ParkingLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLocations, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& parkingLocationDeps);
    private static Unity.Mathematics.float4 GetMaxVehicleSize(Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Net.RoadTypes roadType);
    private static Unity.Entities.Entity GetSecondaryPrefab(Unity.Entities.Entity primaryPrefab, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layoutElements, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabDatas, System.Boolean& validLayout);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    private static System.Boolean SelectParkingSpace(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Objects.Transform& transform, Unity.Entities.Entity& lane, System.Single& curvePosition);
    private System.Void SpawnFireEngines(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnGarbageTrucks(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnHealthcareVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnMaintenanceVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnPoliceCars(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnPostVans(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnTransportVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceCarQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceCarQuery;
```

- `private Unity.Entities.EntityQuery m_FireEngineQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireEngineQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_TransportVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_PostVanQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostVanQuery;
```

- `private Unity.Entities.EntityQuery m_MaintenanceVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_MaintenanceVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageTruckQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageTruckQuery;
```

- `private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData`  

```csharp
private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData;
```

- `private Game.Prefabs.FireEngineSelectData m_FireEngineSelectData`  

```csharp
private Game.Prefabs.FireEngineSelectData m_FireEngineSelectData;
```

- `private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData`  

```csharp
private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData;
```

- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  

```csharp
private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
```

- `private Game.Prefabs.PostVanSelectData m_PostVanSelectData`  

```csharp
private Game.Prefabs.PostVanSelectData m_PostVanSelectData;
```

- `private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData`  

```csharp
private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData;
```

- `private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData`  

```csharp
private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData;
```

- `private Game.Vehicles.ParkedVehiclesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Vehicles.ParkedVehiclesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ParkedVehiclesSystem()`  

```csharp
[Preserve]
	public ParkedVehiclesSystem()
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

- `private CollectDeletedVehicles(Unity.Collections.NativeParallelMultiHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deletedVehicleMap, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void CollectDeletedVehicles(ref NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, JobHandle inputDeps, ref JobHandle deletedVehiclesDeps)
	{
		if (!deletedVehicleMap.IsCreated)
		{
			deletedVehicleMap = new NativeParallelMultiHashMap<Entity, DeletedVehicleData>(0, Allocator.TempJob);
			JobHandle outJobHandle;
			CollectDeletedVehiclesJob jobData = new CollectDeletedVehiclesJob
			{
				m_Chunks = m_DeletedVehicleQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ControllerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LayoutElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DeletedVehicleMap = deletedVehicleMap
			};
			JobHandle jobHandle = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(inputDeps, outJobHandle));
			jobData.m_Chunks.Dispose(jobHandle);
			deletedVehiclesDeps = jobHandle;
		}
	}
```

- `private DuplicateVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void DuplicateVehicles(Entity entity, Temp temp, NativeList<ParkingLocation> parkingLocations, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, ref JobHandle parkingLocationDeps, ref JobHandle deletedVehiclesDeps)
	{
		JobHandle jobHandle = IJobExtensions.Schedule(new DuplicateVehiclesJob
		{
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HelicopterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Helicopter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnspawnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabMovingObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MovingObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrainObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_Entity = entity,
			m_Temp = temp,
			m_Locations = parkingLocations,
			m_DeletedVehicleMap = deletedVehicleMap,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(parkingLocationDeps, deletedVehiclesDeps));
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		parkingLocationDeps = jobHandle;
		deletedVehiclesDeps = jobHandle;
	}
```

- `private static FindDeletedVehicle(Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Objects.Transform transform, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedMap) : Unity.Entities.Entity`  

```csharp
private static Entity FindDeletedVehicle(Entity primaryPrefab, Entity secondaryPrefab, Transform transform, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedMap)
	{
		Entity entity = Entity.Null;
		if (deletedMap.IsCreated && deletedMap.TryGetFirstValue(primaryPrefab, out var item, out var it))
		{
			float num = float.MaxValue;
			NativeParallelMultiHashMapIterator<Entity> it2 = default(NativeParallelMultiHashMapIterator<Entity>);
			do
			{
				if (!(item.m_SecondaryPrefab != secondaryPrefab))
				{
					float num2 = math.distance(item.m_Transform.m_Position, transform.m_Position);
					if (num2 < num)
					{
						entity = item.m_Entity;
						num = num2;
						it2 = it;
					}
				}
			}
			while (deletedMap.TryGetNextValue(out item, ref it));
			if (entity != Entity.Null)
			{
				deletedMap.Remove(it2);
			}
		}
		return entity;
	}
```

- `private FindParkingLocations(Unity.Entities.Entity entity, Unity.Collections.NativeList`1[[Game.Vehicles.ParkedVehiclesSystem+ParkingLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLocations, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& parkingLocationDeps) : System.Void`  

```csharp
private void FindParkingLocations(Entity entity, ref NativeList<ParkingLocation> parkingLocations, JobHandle inputDeps, ref JobHandle parkingLocationDeps)
	{
		if (!parkingLocations.IsCreated)
		{
			parkingLocations = new NativeList<ParkingLocation>(100, Allocator.TempJob);
			JobHandle jobHandle = IJobExtensions.Schedule(new FindParkingLocationsJob
			{
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnLocationElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_SpawnLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_LaneOverlaps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferLookup, ref base.CheckedStateRef),
				m_Entity = entity,
				m_Locations = parkingLocations
			}, inputDeps);
			parkingLocationDeps = jobHandle;
		}
	}
```

- `private static GetMaxVehicleSize(Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Net.RoadTypes roadType) : Unity.Mathematics.float4`  

```csharp
private static float4 GetMaxVehicleSize(NativeList<ParkingLocation> locations, RoadTypes roadType)
	{
		float4 @float = 0f;
		for (int i = 0; i < locations.Length; i++)
		{
			ParkingLocation parkingLocation = locations[i];
			@float = math.select(@float, parkingLocation.m_MaxSize.xyxy, (parkingLocation.m_MaxSize.xxyy > @float.xxww) & ((parkingLocation.m_ParkingLaneData.m_RoadTypes & roadType) != 0));
		}
		return @float;
	}
```

- `private static GetSecondaryPrefab(Unity.Entities.Entity primaryPrefab, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layoutElements, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabDatas, System.Boolean& validLayout) : Unity.Entities.Entity`  

```csharp
private static Entity GetSecondaryPrefab(Entity primaryPrefab, DynamicBuffer<LayoutElement> layoutElements, ref ComponentLookup<PrefabRef> prefabRefs, ref ComponentLookup<PrefabData> prefabDatas, out bool validLayout)
	{
		Entity entity = Entity.Null;
		validLayout = true;
		for (int i = 0; i < layoutElements.Length; i++)
		{
			Entity vehicle = layoutElements[i].m_Vehicle;
			if (prefabRefs.TryGetComponent(vehicle, out var componentData) && componentData.m_Prefab != primaryPrefab)
			{
				if (entity == Entity.Null)
				{
					entity = componentData.m_Prefab;
				}
				validLayout &= prefabDatas.HasEnabledComponent(componentData.m_Prefab);
			}
		}
		return entity;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4B>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_BuildingQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<OwnedVehicle>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Temp>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Applied>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>()
			}
		});
		m_DeletedVehicleQuery = GetEntityQuery(ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Vehicle>(), ComponentType.ReadOnly<Temp>());
		m_PoliceCarQuery = GetEntityQuery(PoliceCarSelectData.GetEntityQueryDesc());
		m_FireEngineQuery = GetEntityQuery(FireEngineSelectData.GetEntityQueryDesc());
		m_HealthcareVehicleQuery = GetEntityQuery(HealthcareVehicleSelectData.GetEntityQueryDesc());
		m_TransportVehicleQuery = GetEntityQuery(TransportVehicleSelectData.GetEntityQueryDesc());
		m_PostVanQuery = GetEntityQuery(PostVanSelectData.GetEntityQueryDesc());
		m_MaintenanceVehicleQuery = GetEntityQuery(MaintenanceVehicleSelectData.GetEntityQueryDesc());
		m_GarbageTruckQuery = GetEntityQuery(GarbageTruckSelectData.GetEntityQueryDesc());
		m_PoliceCarSelectData = new PoliceCarSelectData(this);
		m_FireEngineSelectData = new FireEngineSelectData(this);
		m_HealthcareVehicleSelectData = new HealthcareVehicleSelectData(this);
		m_TransportVehicleSelectData = new TransportVehicleSelectData(this);
		m_PostVanSelectData = new PostVanSelectData(this);
		m_MaintenanceVehicleSelectData = new MaintenanceVehicleSelectData(this);
		m_GarbageTruckSelectData = new GarbageTruckSelectData(this);
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeArray<ArchetypeChunk> nativeArray = m_BuildingQuery.ToArchetypeChunkArray(Allocator.Temp);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Temp> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		base.EntityManager.CompleteDependencyBeforeRO<PrefabRef>();
		base.EntityManager.CompleteDependencyBeforeRO<Temp>();
		try
		{
			NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap = default(NativeParallelMultiHashMap<Entity, DeletedVehicleData>);
			JobHandle deletedVehiclesDeps = default(JobHandle);
			JobHandle dependency = base.Dependency;
			JobHandle jobHandle = default(JobHandle);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<Temp> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					Entity entity = nativeArray2[j];
					Temp value;
					bool flag = CollectionUtils.TryGet(nativeArray3, j, out value);
					if ((value.m_Flags & (TempFlags.Delete | TempFlags.Select | TempFlags.Duplicate)) != 0)
					{
						continue;
					}
					NativeList<ParkingLocation> parkingLocations = default(NativeList<ParkingLocation>);
					JobHandle parkingLocationDeps = default(JobHandle);
					if (flag && value.m_Original != Entity.Null)
					{
						FindParkingLocations(entity, ref parkingLocations, dependency, ref parkingLocationDeps);
						CollectDeletedVehicles(ref deletedVehicleMap, dependency, ref deletedVehiclesDeps);
						DuplicateVehicles(entity, value, parkingLocations, deletedVehicleMap, ref parkingLocationDeps, ref deletedVehiclesDeps);
					}
					if (base.EntityManager.HasComponent<Game.Buildings.PoliceStation>(entity))
					{
						FindParkingLocations(entity, ref parkingLocations, dependency, ref parkingLocationDeps);
						if (flag)
						{
							CollectDeletedVehicles(ref deletedVehicleMap, dependency, ref deletedVehiclesDeps);
						}
						SpawnPoliceCars(entity, value, flag, parkingLocations, deletedVehicleMap, ref parkingLocationDeps, ref deletedVehiclesDeps);
					}
					if (base.EntityManager.HasComponent<Game.Buildings.FireStation>(entity))
					{
						FindParkingLocations(entity, ref parkingLocations, dependency, ref parkingLocationDeps);
						if (flag)
						{
							CollectDeletedVehicles(ref deletedVehicleMap, dependency, ref deletedVehiclesDeps);
						}
						SpawnFireEngines(entity, value, flag, parkingLocations, deletedVehicleMap, ref parkingLocationDeps, ref deletedVehiclesDeps);
					}
					if (base.EntityManager.HasComponent<Game.Buildings.Hospital>(entity) || base.EntityManager.HasComponent<Game.Buildings.DeathcareFacility>(entity))
					{
						FindParkingLocations(entity, ref parkingLocations, dependency, ref parkingLocationDeps);
						if (flag)
						{
							CollectDeletedVehicles(ref deletedVehicleMap, dependency, ref deletedVehiclesDeps);
						}
						SpawnHealthcareVehicles(entity, value, flag, parkingLocations, deletedVehicleMap, ref parkingLocationDeps, ref deletedVehiclesDeps);
					}
					if (base.EntityManager.HasComponent<Game.Buildings.TransportDepot>(entity) || base.EntityManager.HasComponent<Game.Buildings.Prison>(entity) || base.EntityManager.HasComponent<Game.Buildings.EmergencyShelter>(entity))
					{
						FindParkingLocations(entity, ref parkingLocations, dependency, ref parkingLocationDeps);
						if (flag)
						{
							CollectDeletedVehicles(ref deletedVehicleMap, dependency, ref deletedVehiclesDeps);
						}
						SpawnTransportVehicles(entity, value, flag, parkingLocations, deletedVehicleMap, ref parkingLocationDeps, ref deletedVehiclesDeps);
					}
					if (base.EntityManager.HasComponent<Game.Buildings.PostFacility>(entity))
					{
						FindParkingLocations(entity, ref parkingLocations, dependency, ref parkingLocationDeps);
						if (flag)
						{
							CollectDeletedVehicles(ref deletedVehicleMap, dependency, ref deletedVehiclesDeps);
						}
						SpawnPostVans(entity, value, flag, parkingLocations, deletedVehicleMap, ref parkingLocationDeps, ref deletedVehiclesDeps);
					}
					if (base.EntityManager.HasComponent<Game.Buildings.MaintenanceDepot>(entity))
					{
						FindParkingLocations(entity, ref parkingLocations, dependency, ref parkingLocationDeps);
						if (flag)
						{
							CollectDeletedVehicles(ref deletedVehicleMap, dependency, ref deletedVehiclesDeps);
						}
						SpawnMaintenanceVehicles(entity, value, flag, parkingLocations, deletedVehicleMap, ref parkingLocationDeps, ref deletedVehiclesDeps);
					}
					if (base.EntityManager.HasComponent<Game.Buildings.GarbageFacility>(entity))
					{
						FindParkingLocations(entity, ref parkingLocations, dependency, ref parkingLocationDeps);
						if (flag)
						{
							CollectDeletedVehicles(ref deletedVehicleMap, dependency, ref deletedVehiclesDeps);
						}
						SpawnGarbageTrucks(entity, value, flag, parkingLocations, deletedVehicleMap, ref parkingLocationDeps, ref deletedVehiclesDeps);
					}
					if (parkingLocations.IsCreated)
					{
						parkingLocations.Dispose(parkingLocationDeps);
						jobHandle = JobHandle.CombineDependencies(jobHandle, parkingLocationDeps);
					}
				}
			}
			if (deletedVehicleMap.IsCreated)
			{
				deletedVehicleMap.Dispose(deletedVehiclesDeps);
			}
			base.Dependency = jobHandle;
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `private static SelectParkingSpace(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Objects.Transform& transform, Unity.Entities.Entity& lane, System.Single& curvePosition) : System.Boolean`  

```csharp
private static bool SelectParkingSpace(ref Random random, NativeList<ParkingLocation> locations, ObjectGeometryData objectGeometryData, RoadTypes roadType, TrackTypes trackType, out Transform transform, out Entity lane, out float curvePosition)
	{
		float offset;
		float2 parkingSize = VehicleUtils.GetParkingSize(objectGeometryData, out offset);
		int num = 0;
		int num2 = -1;
		for (int i = 0; i < locations.Length; i++)
		{
			ParkingLocation parkingLocation = locations[i];
			if (!math.any(parkingSize > parkingLocation.m_MaxSize) && ((parkingLocation.m_ParkingLaneData.m_RoadTypes & roadType) != RoadTypes.None || (parkingLocation.m_TrackTypes & trackType) != TrackTypes.None))
			{
				int num3 = 100;
				num += num3;
				if (random.NextInt(num) < num3)
				{
					num2 = i;
				}
			}
		}
		if (num2 != -1)
		{
			ParkingLocation parkingLocation2 = locations[num2];
			lane = parkingLocation2.m_Lane;
			curvePosition = parkingLocation2.m_CurvePos;
			if (parkingLocation2.m_SpawnLocationType == SpawnLocationType.ParkingLane)
			{
				if (parkingLocation2.m_ParkingLaneData.m_SlotAngle <= 0.25f)
				{
					if (offset > 0f)
					{
						Bounds1 t = new Bounds1(curvePosition, 1f);
						MathUtils.ClampLength(parkingLocation2.m_Curve.m_Bezier, ref t, offset);
						curvePosition = t.max;
					}
					else if (offset < 0f)
					{
						Bounds1 t2 = new Bounds1(0f, curvePosition);
						MathUtils.ClampLengthInverse(parkingLocation2.m_Curve.m_Bezier, ref t2, 0f - offset);
						curvePosition = t2.min;
					}
				}
				transform = VehicleUtils.CalculateParkingSpaceTarget(parkingLocation2.m_ParkingLane, parkingLocation2.m_ParkingLaneData, objectGeometryData, parkingLocation2.m_Curve, parkingLocation2.m_OwnerTransform, curvePosition);
			}
			else
			{
				transform = parkingLocation2.m_OwnerTransform;
			}
			locations.RemoveAtSwapBack(num2);
			return true;
		}
		transform = default(Transform);
		lane = Entity.Null;
		curvePosition = 0f;
		return false;
	}
```

- `private SpawnFireEngines(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void SpawnFireEngines(Entity entity, Temp temp, bool isTemp, NativeList<ParkingLocation> parkingLocations, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, ref JobHandle parkingLocationDeps, ref JobHandle deletedVehiclesDeps)
	{
		m_FireEngineSelectData.PreUpdate(this, m_CityConfigurationSystem, m_FireEngineQuery, Allocator.TempJob, out var jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new SpawnFireEnginesJob
		{
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabFireStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_FireStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef),
			m_Entity = entity,
			m_Temp = temp,
			m_IsTemp = isTemp,
			m_FireEngineSelectData = m_FireEngineSelectData,
			m_Locations = parkingLocations,
			m_DeletedVehicleMap = (isTemp ? deletedVehicleMap : default(NativeParallelMultiHashMap<Entity, DeletedVehicleData>)),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, isTemp ? JobHandle.CombineDependencies(parkingLocationDeps, deletedVehiclesDeps, jobHandle) : JobHandle.CombineDependencies(parkingLocationDeps, jobHandle));
		m_FireEngineSelectData.PostUpdate(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		parkingLocationDeps = jobHandle2;
		if (isTemp)
		{
			deletedVehiclesDeps = jobHandle2;
		}
	}
```

- `private SpawnGarbageTrucks(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void SpawnGarbageTrucks(Entity entity, Temp temp, bool isTemp, NativeList<ParkingLocation> parkingLocations, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, ref JobHandle parkingLocationDeps, ref JobHandle deletedVehiclesDeps)
	{
		m_GarbageTruckSelectData.PreUpdate(this, m_CityConfigurationSystem, m_GarbageTruckQuery, Allocator.TempJob, out var jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new SpawnGarbageTrucksJob
		{
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGarbageFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GarbageFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef),
			m_Entity = entity,
			m_Temp = temp,
			m_IsTemp = isTemp,
			m_GarbageTruckSelectData = m_GarbageTruckSelectData,
			m_Locations = parkingLocations,
			m_DeletedVehicleMap = (isTemp ? deletedVehicleMap : default(NativeParallelMultiHashMap<Entity, DeletedVehicleData>)),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, isTemp ? JobHandle.CombineDependencies(parkingLocationDeps, deletedVehiclesDeps, jobHandle) : JobHandle.CombineDependencies(parkingLocationDeps, jobHandle));
		m_GarbageTruckSelectData.PostUpdate(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		parkingLocationDeps = jobHandle2;
		if (isTemp)
		{
			deletedVehiclesDeps = jobHandle2;
		}
	}
```

- `private SpawnHealthcareVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void SpawnHealthcareVehicles(Entity entity, Temp temp, bool isTemp, NativeList<ParkingLocation> parkingLocations, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, ref JobHandle parkingLocationDeps, ref JobHandle deletedVehiclesDeps)
	{
		m_HealthcareVehicleSelectData.PreUpdate(this, m_CityConfigurationSystem, m_HealthcareVehicleQuery, Allocator.TempJob, out var jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new SpawnHealthcareVehiclesJob
		{
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabHospitalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HospitalData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDeathcareFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DeathcareFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef),
			m_Entity = entity,
			m_Temp = temp,
			m_IsTemp = isTemp,
			m_HealthcareVehicleSelectData = m_HealthcareVehicleSelectData,
			m_Locations = parkingLocations,
			m_DeletedVehicleMap = (isTemp ? deletedVehicleMap : default(NativeParallelMultiHashMap<Entity, DeletedVehicleData>)),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, isTemp ? JobHandle.CombineDependencies(parkingLocationDeps, deletedVehiclesDeps, jobHandle) : JobHandle.CombineDependencies(parkingLocationDeps, jobHandle));
		m_HealthcareVehicleSelectData.PostUpdate(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		parkingLocationDeps = jobHandle2;
		if (isTemp)
		{
			deletedVehiclesDeps = jobHandle2;
		}
	}
```

- `private SpawnMaintenanceVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void SpawnMaintenanceVehicles(Entity entity, Temp temp, bool isTemp, NativeList<ParkingLocation> parkingLocations, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, ref JobHandle parkingLocationDeps, ref JobHandle deletedVehiclesDeps)
	{
		m_MaintenanceVehicleSelectData.PreUpdate(this, m_CityConfigurationSystem, m_MaintenanceVehicleQuery, Allocator.TempJob, out var jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new SpawnMaintenanceVehiclesJob
		{
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabMaintenanceDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MaintenanceDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef),
			m_Entity = entity,
			m_Temp = temp,
			m_IsTemp = isTemp,
			m_MaintenanceVehicleSelectData = m_MaintenanceVehicleSelectData,
			m_Locations = parkingLocations,
			m_DeletedVehicleMap = (isTemp ? deletedVehicleMap : default(NativeParallelMultiHashMap<Entity, DeletedVehicleData>)),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, isTemp ? JobHandle.CombineDependencies(parkingLocationDeps, deletedVehiclesDeps, jobHandle) : JobHandle.CombineDependencies(parkingLocationDeps, jobHandle));
		m_MaintenanceVehicleSelectData.PostUpdate(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		parkingLocationDeps = jobHandle2;
		if (isTemp)
		{
			deletedVehiclesDeps = jobHandle2;
		}
	}
```

- `private SpawnPoliceCars(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void SpawnPoliceCars(Entity entity, Temp temp, bool isTemp, NativeList<ParkingLocation> parkingLocations, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, ref JobHandle parkingLocationDeps, ref JobHandle deletedVehiclesDeps)
	{
		m_PoliceCarSelectData.PreUpdate(this, m_CityConfigurationSystem, m_PoliceCarQuery, Allocator.TempJob, out var jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new SpawnPoliceCarsJob
		{
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPoliceStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PoliceStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef),
			m_Entity = entity,
			m_Temp = temp,
			m_IsTemp = isTemp,
			m_PoliceCarSelectData = m_PoliceCarSelectData,
			m_Locations = parkingLocations,
			m_DeletedVehicleMap = (isTemp ? deletedVehicleMap : default(NativeParallelMultiHashMap<Entity, DeletedVehicleData>)),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, isTemp ? JobHandle.CombineDependencies(parkingLocationDeps, deletedVehiclesDeps, jobHandle) : JobHandle.CombineDependencies(parkingLocationDeps, jobHandle));
		m_PoliceCarSelectData.PostUpdate(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		parkingLocationDeps = jobHandle2;
		if (isTemp)
		{
			deletedVehiclesDeps = jobHandle2;
		}
	}
```

- `private SpawnPostVans(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void SpawnPostVans(Entity entity, Temp temp, bool isTemp, NativeList<ParkingLocation> parkingLocations, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, ref JobHandle parkingLocationDeps, ref JobHandle deletedVehiclesDeps)
	{
		m_PostVanSelectData.PreUpdate(this, m_CityConfigurationSystem, m_PostVanQuery, Allocator.TempJob, out var jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new SpawnPostVansJob
		{
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPostFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PostFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef),
			m_Entity = entity,
			m_Temp = temp,
			m_IsTemp = isTemp,
			m_PostVanSelectData = m_PostVanSelectData,
			m_Locations = parkingLocations,
			m_DeletedVehicleMap = (isTemp ? deletedVehicleMap : default(NativeParallelMultiHashMap<Entity, DeletedVehicleData>)),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, isTemp ? JobHandle.CombineDependencies(parkingLocationDeps, deletedVehiclesDeps, jobHandle) : JobHandle.CombineDependencies(parkingLocationDeps, jobHandle));
		m_PostVanSelectData.PostUpdate(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		parkingLocationDeps = jobHandle2;
		if (isTemp)
		{
			deletedVehiclesDeps = jobHandle2;
		}
	}
```

- `private SpawnTransportVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private void SpawnTransportVehicles(Entity entity, Temp temp, bool isTemp, NativeList<ParkingLocation> parkingLocations, NativeParallelMultiHashMap<Entity, DeletedVehicleData> deletedVehicleMap, ref JobHandle parkingLocationDeps, ref JobHandle deletedVehiclesDeps)
	{
		m_TransportVehicleSelectData.PreUpdate(this, m_CityConfigurationSystem, m_TransportVehicleQuery, Allocator.TempJob, out var jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new SpawnTransportVehiclesJob
		{
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransportDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPrisonData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrisonData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabEmergencyShelterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EmergencyShelterData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef),
			m_Entity = entity,
			m_Temp = temp,
			m_IsTemp = isTemp,
			m_TransportVehicleSelectData = m_TransportVehicleSelectData,
			m_Locations = parkingLocations,
			m_DeletedVehicleMap = (isTemp ? deletedVehicleMap : default(NativeParallelMultiHashMap<Entity, DeletedVehicleData>)),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		}, isTemp ? JobHandle.CombineDependencies(parkingLocationDeps, deletedVehiclesDeps, jobHandle) : JobHandle.CombineDependencies(parkingLocationDeps, jobHandle));
		m_TransportVehicleSelectData.PostUpdate(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		parkingLocationDeps = jobHandle2;
		if (isTemp)
		{
			deletedVehiclesDeps = jobHandle2;
		}
	}
```


## Nested types

- `Game.Vehicles.ParkedVehiclesSystem+ParkingLocation`  
- `Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData`  
- `Game.Vehicles.ParkedVehiclesSystem+FindParkingLocationsJob`  
- `Game.Vehicles.ParkedVehiclesSystem+CollectDeletedVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+DuplicateVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnPoliceCarsJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnFireEnginesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnHealthcareVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnTransportVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnPostVansJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnMaintenanceVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnGarbageTrucksJob`  
- `Game.Vehicles.ParkedVehiclesSystem+TypeHandle`  

