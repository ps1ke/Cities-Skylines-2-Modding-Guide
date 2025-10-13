# Game.Simulation.StorageCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StorageCompanySystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Entities.EntityQuery m_StationGroup;
    private Unity.Entities.EntityQuery m_OCStationGroup;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.StorageCompanySystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kTransferCooldown;
    private static readonly System.Int32 kCostFadeProbability;
    private static readonly System.Single kMaxTransportUnitCost;
    public static readonly System.Int32 kStorageLowStockAmount;
    public static readonly System.Int32 kStationLowStockAmount;
    public static readonly System.Int32 kStorageExportStartAmount;
    public static readonly System.Int32 kStationExportStartAmount;
    private static readonly System.Int32 kStorageMinimalTransferAmount;
    private static readonly System.Int32 kStationMinimalTransferAmount;

    public StorageCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private static System.Boolean ProcessStorage(System.Int32 chunkIndex, Unity.Entities.Entity company, Unity.Entities.Entity building, Game.Economy.Resource resource, Game.Prefabs.StorageCompanyData storageCompanyData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resourceBuffer, Unity.Entities.DynamicBuffer<Game.Companies.StorageTransferRequest> requests, Game.Companies.StorageLimitData limitData, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.DeliveryTruckSelectData truckSelectData, System.UInt32 simulationFrame, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> tradeCosts, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Boolean station, System.Boolean hasConnectedRoute, System.Int32 incomingAmount, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Companies.StorageCompany, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageCompanies, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicles, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.ComponentLookup`1[[Game.Common.Target, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targets, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layoutElements, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Objects.OutsideConnection, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections);
    private static System.Boolean RemoveFromRequests(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.Entity owner, Unity.Entities.Entity target1, Unity.Entities.Entity target2, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Entities.EntityQuery m_StationGroup`  

```csharp
private Unity.Entities.EntityQuery m_StationGroup;
```

- `private Unity.Entities.EntityQuery m_OCStationGroup`  

```csharp
private Unity.Entities.EntityQuery m_OCStationGroup;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.StorageCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StorageCompanySystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kTransferCooldown`  

```csharp
private static readonly System.Int32 kTransferCooldown;
```

- `private static readonly System.Int32 kCostFadeProbability`  

```csharp
private static readonly System.Int32 kCostFadeProbability;
```

- `private static readonly System.Single kMaxTransportUnitCost`  

```csharp
private static readonly System.Single kMaxTransportUnitCost;
```

- `public static readonly System.Int32 kStorageLowStockAmount`  

```csharp
public static readonly System.Int32 kStorageLowStockAmount;
```

- `public static readonly System.Int32 kStationLowStockAmount`  

```csharp
public static readonly System.Int32 kStationLowStockAmount;
```

- `public static readonly System.Int32 kStorageExportStartAmount`  

```csharp
public static readonly System.Int32 kStorageExportStartAmount;
```

- `public static readonly System.Int32 kStationExportStartAmount`  

```csharp
public static readonly System.Int32 kStationExportStartAmount;
```

- `private static readonly System.Int32 kStorageMinimalTransferAmount`  

```csharp
private static readonly System.Int32 kStorageMinimalTransferAmount;
```

- `private static readonly System.Int32 kStationMinimalTransferAmount`  

```csharp
private static readonly System.Int32 kStationMinimalTransferAmount;
```


## Constructors

- `public StorageCompanySystem()`  

```csharp
[Preserve]
	public StorageCompanySystem()
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
		m_VehicleCapacitySystem = base.World.GetOrCreateSystemManaged<VehicleCapacitySystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CompanyGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadWrite<Resources>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadOnly<CompanyData>(), ComponentType.Exclude<StorageTransfer>(), ComponentType.Exclude<Deleted>());
		m_StationGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.ReadWrite<Resources>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<CompanyData>(), ComponentType.Exclude<StorageTransfer>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Deleted>());
		m_OCStationGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.ReadWrite<Resources>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<CompanyData>(), ComponentType.Exclude<StorageTransfer>(), ComponentType.Exclude<CityServiceUpkeep>(), ComponentType.Exclude<Deleted>());
		RequireAnyForUpdate(m_CompanyGroup, m_StationGroup, m_OCStationGroup);
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
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		JobHandle jobHandle = JobChunkExtensions.Schedule(new StorageJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CompanyResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_TradeCostType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_TradeCost_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Limits = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_StorageCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageTransferRequests = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_StorageTransferRequest_RW_BufferLookup, ref base.CheckedStateRef),
			m_Targets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Trucks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GuestVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_GuestVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_UpdateFrameIndex = updateFrameWithInterval,
			m_DeliveryTruckSelectData = m_VehicleCapacitySystem.GetDeliveryTruckSelectData(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_RandomSeed = RandomSeed.Next()
		}, m_CompanyGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		JobHandle jobHandle2 = JobChunkExtensions.Schedule(new StationStorageJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CompanyResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TradeCostType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_TradeCost_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_Limits = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_StorageCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageTransferRequests = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_StorageTransferRequest_RW_BufferLookup, ref base.CheckedStateRef),
			m_TripNeededsBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferLookup, ref base.CheckedStateRef),
			m_Targets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Trucks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedRouteBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RO_BufferLookup, ref base.CheckedStateRef),
			m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjectBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_TransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Connecteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_DeliveryTruckSelectData = m_VehicleCapacitySystem.GetDeliveryTruckSelectData(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_RandomSeed = RandomSeed.Next(),
			m_UpdateInterval = GetUpdateInterval(SystemUpdatePhase.GameSimulation)
		}, m_StationGroup, JobHandle.CombineDependencies(jobHandle, base.Dependency));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		JobHandle jobHandle3 = JobChunkExtensions.Schedule(new OCStationStorageJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CompanyResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TradeCostType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_TradeCost_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_Limits = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageTransferRequests = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_StorageTransferRequest_RW_BufferLookup, ref base.CheckedStateRef),
			m_Targets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjectBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_TransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedRouteBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RO_BufferLookup, ref base.CheckedStateRef),
			m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourceBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Connecteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_RandomSeed = RandomSeed.Next(),
			m_UpdateInterval = GetUpdateInterval(SystemUpdatePhase.GameSimulation)
		}, m_OCStationGroup, JobHandle.CombineDependencies(jobHandle2, base.Dependency));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle3);
		base.Dependency = JobHandle.CombineDependencies(jobHandle, jobHandle2, jobHandle3);
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (!(context.version < Version.storageConditionReset))
		{
			return;
		}
		NativeArray<Entity> nativeArray = m_CompanyGroup.ToEntityArray(Allocator.Temp);
		foreach (Entity item in nativeArray)
		{
			base.EntityManager.GetBuffer<TradeCost>(item).Clear();
		}
		nativeArray.Dispose();
		nativeArray = m_StationGroup.ToEntityArray(Allocator.Temp);
		foreach (Entity item2 in nativeArray)
		{
			base.EntityManager.GetBuffer<TradeCost>(item2).Clear();
		}
		nativeArray.Dispose();
	}
```

- `private static ProcessStorage(System.Int32 chunkIndex, Unity.Entities.Entity company, Unity.Entities.Entity building, Game.Economy.Resource resource, Game.Prefabs.StorageCompanyData storageCompanyData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resourceBuffer, Unity.Entities.DynamicBuffer<Game.Companies.StorageTransferRequest> requests, Game.Companies.StorageLimitData limitData, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.DeliveryTruckSelectData truckSelectData, System.UInt32 simulationFrame, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> tradeCosts, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Boolean station, System.Boolean hasConnectedRoute, System.Int32 incomingAmount, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Companies.StorageCompany, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageCompanies, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicles, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.ComponentLookup`1[[Game.Common.Target, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targets, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layoutElements, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Objects.OutsideConnection, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections) : System.Boolean`  

```csharp
private static bool ProcessStorage(int chunkIndex, Entity company, Entity building, Resource resource, StorageCompanyData storageCompanyData, DynamicBuffer<Resources> resourceBuffer, DynamicBuffer<StorageTransferRequest> requests, StorageLimitData limitData, SpawnableBuildingData spawnableData, BuildingData buildingData, DeliveryTruckSelectData truckSelectData, uint simulationFrame, DynamicBuffer<TradeCost> tradeCosts, EntityCommandBuffer.ParallelWriter commandBuffer, bool station, bool hasConnectedRoute, int incomingAmount, ref Random random, ref ComponentLookup<Game.Companies.StorageCompany> storageCompanies, ref BufferLookup<OwnedVehicle> ownedVehicles, ref BufferLookup<StorageTransferRequest> storageTransferRequests, ref ComponentLookup<Game.Vehicles.DeliveryTruck> trucks, ref ComponentLookup<Target> targets, ref BufferLookup<LayoutElement> layoutElements, ref ComponentLookup<PropertyRenter> propertyRenters, ref ComponentLookup<Game.Objects.OutsideConnection> outsideConnections)
	{
		bool flag = false;
		int num = EconomyUtils.CountResources(storageCompanyData.m_StoredResources);
		if (num == 0)
		{
			return false;
		}
		int num2 = limitData.GetAdjustedLimitForWarehouse(spawnableData, buildingData) / num;
		if ((storageCompanyData.m_StoredResources & resource) != Resource.NoResource)
		{
			int resources = EconomyUtils.GetResources(resource, resourceBuffer);
			int num3 = resources;
			for (int i = 0; i < requests.Length; i++)
			{
				StorageTransferRequest value = requests[i];
				if (value.m_Resource != resource)
				{
					continue;
				}
				if (!storageCompanies.HasComponent(value.m_Target) || !storageTransferRequests.HasBuffer(value.m_Target) || (!propertyRenters.HasComponent(value.m_Target) && !outsideConnections.HasComponent(value.m_Target)))
				{
					requests.RemoveAtSwapBack(i);
					i--;
					continue;
				}
				bool flag2 = (value.m_Flags & StorageTransferFlags.Incoming) != 0;
				if (flag2)
				{
					int num4 = 0;
					DynamicBuffer<StorageTransferRequest> dynamicBuffer = storageTransferRequests[value.m_Target];
					for (int j = 0; j < dynamicBuffer.Length; j++)
					{
						StorageTransferRequest storageTransferRequest = dynamicBuffer[j];
						if ((storageTransferRequest.m_Target == company || storageTransferRequest.m_Target == building) && storageTransferRequest.m_Resource == resource && (storageTransferRequest.m_Flags & StorageTransferFlags.Incoming) == 0)
						{
							num4 += storageTransferRequest.m_Amount;
						}
					}
					int num5 = 0;
					if (ownedVehicles.HasBuffer(value.m_Target))
					{
						DynamicBuffer<OwnedVehicle> dynamicBuffer2 = ownedVehicles[value.m_Target];
						for (int k = 0; k < dynamicBuffer2.Length; k++)
						{
							Entity vehicle = dynamicBuffer2[k].m_Vehicle;
							if (!trucks.HasComponent(vehicle) || !targets.HasComponent(vehicle))
							{
								continue;
							}
							Game.Vehicles.DeliveryTruck deliveryTruck = trucks[vehicle];
							Entity target = targets[vehicle].m_Target;
							if (!(target == company) && !(target == building))
							{
								continue;
							}
							int num6 = 0;
							if (deliveryTruck.m_Resource == resource)
							{
								num6 += deliveryTruck.m_Amount;
							}
							if (layoutElements.HasBuffer(vehicle))
							{
								DynamicBuffer<LayoutElement> dynamicBuffer3 = layoutElements[vehicle];
								for (int l = 0; l < dynamicBuffer3.Length; l++)
								{
									Entity vehicle2 = dynamicBuffer3[l].m_Vehicle;
									if (trucks.HasComponent(vehicle2))
									{
										deliveryTruck = trucks[vehicle2];
										if (deliveryTruck.m_Resource == resource)
										{
											num6 += deliveryTruck.m_Amount;
										}
									}
								}
							}
							num5 += num6;
						}
					}
					if (station && num4 + num5 < value.m_Amount && incomingAmount > 0)
					{
						int num7 = math.min(value.m_Amount - num5 - num4, incomingAmount);
						num5 += num7;
						incomingAmount -= num7;
					}
					if (num5 + num4 == 0)
					{
						requests.RemoveAtSwapBack(i);
						i--;
						continue;
					}
					if (num5 + num4 < value.m_Amount)
					{
						value.m_Amount = num5 + num4;
						requests[i] = value;
					}
				}
				else
				{
					int num8 = 0;
					DynamicBuffer<StorageTransferRequest> dynamicBuffer4 = storageTransferRequests[value.m_Target];
					for (int m = 0; m < dynamicBuffer4.Length; m++)
					{
						StorageTransferRequest storageTransferRequest2 = dynamicBuffer4[m];
						if ((storageTransferRequest2.m_Target == company || storageTransferRequest2.m_Target == building) && storageTransferRequest2.m_Resource == resource && (storageTransferRequest2.m_Flags & StorageTransferFlags.Incoming) != 0)
						{
							num8 = storageTransferRequest2.m_Amount;
							break;
						}
					}
					if (num8 == 0)
					{
						requests.RemoveAtSwapBack(i);
						i--;
						continue;
					}
					if (num8 < value.m_Amount)
					{
						value.m_Amount = num8;
						requests[i] = value;
					}
				}
				num3 += (flag2 ? value.m_Amount : (-value.m_Amount));
			}
			int num9 = num2 - resources;
			TradeCost tradeCost = EconomyUtils.GetTradeCost(resource, tradeCosts);
			long lastTradeRequestTime = EconomyUtils.GetLastTradeRequestTime(tradeCosts);
			if (station && tradeCost.m_LastTransferRequestTime == 0L)
			{
				tradeCost.m_LastTransferRequestTime = simulationFrame - kTransferCooldown / 2;
				EconomyUtils.SetTradeCost(resource, tradeCost, tradeCosts, keepLastTime: false);
			}
			if (simulationFrame - lastTradeRequestTime >= kTransferCooldown + random.NextInt(storageCompanyData.m_TransportInterval.x, storageCompanyData.m_TransportInterval.y) || tradeCost.m_LastTransferRequestTime == 0L)
			{
				int num10 = (station ? kStationExportStartAmount : kStorageExportStartAmount);
				num10 = (int)math.min((float)num2 * 0.8f, num10);
				int num11 = (station ? kStationLowStockAmount : kStorageLowStockAmount);
				num11 = (int)math.min((float)num2 * 0.5f, num11);
				int num12 = (station ? kStationMinimalTransferAmount : kStorageMinimalTransferAmount);
				num12 = (int)math.min((float)num2 * 0.5f, num12);
				int num13 = (num10 - num11) / 2 + num11;
				if (resources > num10 && num3 > num10)
				{
					int num14 = 0;
					int num15 = resources - num11;
					if (!station)
					{
						truckSelectData.TrySelectItem(ref random, resource, num15, out var item);
						if (item.m_Capacity > 0)
						{
							num15 = item.m_Capacity * math.max(num15 / item.m_Capacity, 1);
						}
						num14 = item.m_Cost;
					}
					if (station || (float)num14 / (float)math.min(resources, num15) < kMaxTransportUnitCost)
					{
						commandBuffer.AddComponent(chunkIndex, company, new StorageTransfer
						{
							m_Resource = resource,
							m_Amount = num15
						});
						tradeCost.m_LastTransferRequestTime = simulationFrame;
						EconomyUtils.SetTradeCost(resource, tradeCost, tradeCosts, keepLastTime: false);
						flag = true;
					}
				}
				else if (resources < num11 && num3 < num11)
				{
					if (station && !hasConnectedRoute)
					{
						return false;
					}
					StorageTransfer component = new StorageTransfer
					{
						m_Resource = resource
					};
					int num16 = math.min((int)((float)num9 * 0.9f), math.max(num13 - resources, num12));
					component.m_Amount = -num16;
					if (!station)
					{
						truckSelectData.TrySelectItem(ref random, resource, num16, out var item2);
						if (item2.m_Capacity > 0)
						{
							component.m_Amount = -math.max(num16 / item2.m_Capacity, 1) * item2.m_Capacity;
						}
					}
					commandBuffer.AddComponent(chunkIndex, company, component);
					tradeCost.m_LastTransferRequestTime = simulationFrame;
					flag = true;
				}
				if (random.NextInt(kCostFadeProbability) == 0)
				{
					tradeCost.m_BuyCost *= 0.99f;
					tradeCost.m_SellCost *= 0.99f;
					if (!flag)
					{
						EconomyUtils.SetTradeCost(resource, tradeCost, tradeCosts, keepLastTime: false);
					}
				}
				if (flag)
				{
					EconomyUtils.SetTradeCost(resource, tradeCost, tradeCosts, keepLastTime: false);
				}
			}
		}
		return flag;
	}
```

- `private static RemoveFromRequests(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.Entity owner, Unity.Entities.Entity target1, Unity.Entities.Entity target2, Unity.Entities.BufferLookup`1[[Game.Companies.StorageTransferRequest, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& storageTransferRequests) : System.Boolean`  

```csharp
private static bool RemoveFromRequests(Resource resource, int amount, Entity owner, Entity target1, Entity target2, ref BufferLookup<StorageTransferRequest> storageTransferRequests)
	{
		DynamicBuffer<StorageTransferRequest> dynamicBuffer = storageTransferRequests[owner];
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			StorageTransferRequest value = dynamicBuffer[i];
			if ((value.m_Target == target1 || value.m_Target == target2) && value.m_Resource == resource && (value.m_Flags & StorageTransferFlags.Incoming) == 0)
			{
				if (value.m_Amount > amount)
				{
					value.m_Amount -= amount;
					dynamicBuffer[i] = value;
					return true;
				}
				amount -= value.m_Amount;
				dynamicBuffer.RemoveAtSwapBack(i);
				i--;
			}
		}
		return amount == 0;
	}
```


## Nested types

- `Game.Simulation.StorageCompanySystem+StorageJob`  
- `Game.Simulation.StorageCompanySystem+StationStorageJob`  
- `Game.Simulation.StorageCompanySystem+OCStationStorageJob`  
- `Game.Simulation.StorageCompanySystem+TypeHandle`  

