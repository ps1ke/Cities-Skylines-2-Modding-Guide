# Game.Simulation.CityServiceUpkeepSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityServiceUpkeepSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Unity.Entities.EntityQuery m_UpkeepGroup;
    private Unity.Entities.EntityQuery m_BudgetDataQuery;
    private Game.Simulation.CityServiceUpkeepSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kUpdatesPerDay;

    public CityServiceUpkeepSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 CalculateUpkeep(System.Int32 amount, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity budgetEntity, Unity.Entities.EntityManager entityManager);
    public static System.Byte GetResourceAvailability(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> upkeeps, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Collections.NativeArray<System.Int32> storageTargets);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Void GetUpkeepModifierData(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> upkeepModifierList, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabs, Unity.Entities.BufferLookup<Game.Prefabs.UpkeepModifierData> upkeepModifiers, Unity.Entities.Entity entity);
    public static System.Int32 GetUpkeepOfEmployeeWage(Unity.Entities.BufferLookup<Game.Companies.Employee> employeeBufs, Unity.Entities.Entity entity, Game.Prefabs.EconomyParameterData economyParameterData, System.Boolean mainBuildingDisabled);
    public static System.Void GetUpkeepWithUsageScale(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> totalUpkeepDatas, Unity.Entities.BufferLookup<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgradeBufs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Buildings.ServiceUsage> serviceUsages, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, System.Boolean mainBuildingDisabled);
    public static System.Boolean IsMaterialResource(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.ResourceStack upkeep);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Unity.Entities.EntityQuery m_UpkeepGroup`  

```csharp
private Unity.Entities.EntityQuery m_UpkeepGroup;
```

- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_BudgetDataQuery;
```

- `private Game.Simulation.CityServiceUpkeepSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CityServiceUpkeepSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kUpdatesPerDay`  

```csharp
private static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public CityServiceUpkeepSystem()`  

```csharp
[Preserve]
	public CityServiceUpkeepSystem()
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

- `public static CalculateUpkeep(System.Int32 amount, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity budgetEntity, Unity.Entities.EntityManager entityManager) : System.Int32`  

```csharp
public static int CalculateUpkeep(int amount, Entity prefabEntity, Entity budgetEntity, EntityManager entityManager)
	{
		Entity entity = Entity.Null;
		if (entityManager.TryGetComponent<ServiceObjectData>(prefabEntity, out var component))
		{
			entity = component.m_Service;
		}
		int num = 100;
		if (entityManager.TryGetBuffer(budgetEntity, isReadOnly: true, out DynamicBuffer<ServiceBudgetData> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				if (buffer[i].m_Service == entity)
				{
					num = buffer[i].m_Budget;
				}
			}
		}
		return (int)math.round((float)amount * ((float)num / 100f));
	}
```

- `public static GetResourceAvailability(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> upkeeps, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Collections.NativeArray<System.Int32> storageTargets) : System.Byte`  

```csharp
public static byte GetResourceAvailability(NativeList<ServiceUpkeepData> upkeeps, DynamicBuffer<Game.Economy.Resources> resources, NativeArray<int> storageTargets)
	{
		byte b = byte.MaxValue;
		foreach (ServiceUpkeepData item in upkeeps)
		{
			Resource resource = item.m_Upkeep.m_Resource;
			int num = storageTargets[EconomyUtils.GetResourceIndex(resource)];
			if (num > 0)
			{
				int resources2 = EconomyUtils.GetResources(resource, resources);
				byte b2 = (byte)math.clamp(math.ceil(255f * (float)resources2 / (float)num), 0f, 255f);
				if (b2 < b)
				{
					b = b2;
				}
			}
		}
		return b;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `public static GetUpkeepModifierData(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> upkeepModifierList, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabs, Unity.Entities.BufferLookup<Game.Prefabs.UpkeepModifierData> upkeepModifiers, Unity.Entities.Entity entity) : System.Void`  

```csharp
public static void GetUpkeepModifierData(NativeList<UpkeepModifierData> upkeepModifierList, BufferLookup<InstalledUpgrade> installedUpgrades, ComponentLookup<PrefabRef> prefabs, BufferLookup<UpkeepModifierData> upkeepModifiers, Entity entity)
	{
		if (installedUpgrades.TryGetBuffer(entity, out var bufferData))
		{
			UpgradeUtils.CombineStats(upkeepModifierList, bufferData, ref prefabs, ref upkeepModifiers);
		}
	}
```

- `public static GetUpkeepOfEmployeeWage(Unity.Entities.BufferLookup<Game.Companies.Employee> employeeBufs, Unity.Entities.Entity entity, Game.Prefabs.EconomyParameterData economyParameterData, System.Boolean mainBuildingDisabled) : System.Int32`  

```csharp
public static int GetUpkeepOfEmployeeWage(BufferLookup<Employee> employeeBufs, Entity entity, EconomyParameterData economyParameterData, bool mainBuildingDisabled)
	{
		if (mainBuildingDisabled)
		{
			return 0;
		}
		int num = 0;
		if (employeeBufs.TryGetBuffer(entity, out var bufferData))
		{
			for (int i = 0; i < bufferData.Length; i++)
			{
				num += economyParameterData.GetWage(bufferData[i].m_Level, cityServiceJob: true);
			}
		}
		return num;
	}
```

- `public static GetUpkeepWithUsageScale(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> totalUpkeepDatas, Unity.Entities.BufferLookup<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> installedUpgradeBufs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Buildings.ServiceUsage> serviceUsages, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, System.Boolean mainBuildingDisabled) : System.Void`  

```csharp
public static void GetUpkeepWithUsageScale(NativeList<ServiceUpkeepData> totalUpkeepDatas, BufferLookup<ServiceUpkeepData> serviceUpkeepDatas, BufferLookup<InstalledUpgrade> installedUpgradeBufs, ComponentLookup<PrefabRef> prefabRefs, ComponentLookup<ServiceUsage> serviceUsages, Entity entity, Entity prefab, bool mainBuildingDisabled)
	{
		if (serviceUpkeepDatas.TryGetBuffer(prefab, out var bufferData))
		{
			foreach (ServiceUpkeepData item in bufferData)
			{
				ServiceUpkeepData value = item;
				if (value.m_ScaleWithUsage && serviceUsages.TryGetComponent(entity, out var componentData))
				{
					totalUpkeepDatas.Add(value.ApplyServiceUsage(componentData.m_Usage));
				}
				else
				{
					totalUpkeepDatas.Add(in value);
				}
			}
		}
		if (!installedUpgradeBufs.TryGetBuffer(entity, out var bufferData2))
		{
			return;
		}
		foreach (InstalledUpgrade item2 in bufferData2)
		{
			bool flag = BuildingUtils.CheckOption(item2, BuildingOption.Inactive);
			if (!prefabRefs.TryGetComponent(item2.m_Upgrade, out var componentData2) || !serviceUpkeepDatas.TryGetBuffer(componentData2.m_Prefab, out var bufferData3))
			{
				continue;
			}
			for (int i = 0; i < bufferData3.Length; i++)
			{
				ServiceUpkeepData combineData = bufferData3[i];
				if (combineData.m_Upkeep.m_Resource == Resource.Money)
				{
					if (!mainBuildingDisabled && flag)
					{
						combineData.m_Upkeep.m_Amount = (combineData.m_Upkeep.m_Amount + 5) / 10;
					}
				}
				else if (flag)
				{
					continue;
				}
				if (combineData.m_ScaleWithUsage && serviceUsages.TryGetComponent(item2.m_Upgrade, out var componentData3))
				{
					UpgradeUtils.CombineStats(totalUpkeepDatas, combineData.ApplyServiceUsage(componentData3.m_Usage));
				}
				else
				{
					UpgradeUtils.CombineStats(totalUpkeepDatas, combineData);
				}
			}
		}
	}
```

- `public static IsMaterialResource(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.ResourceStack upkeep) : System.Boolean`  

```csharp
public static bool IsMaterialResource(ComponentLookup<ResourceData> resourceDatas, ResourcePrefabs resourcePrefabs, ResourceStack upkeep)
	{
		return resourceDatas[resourcePrefabs[upkeep.m_Resource]].m_Weight > 0f;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_VehicleCapacitySystem = base.World.GetOrCreateSystemManaged<VehicleCapacitySystem>();
		m_UpkeepGroup = GetEntityQuery(ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.ReadWrite<Game.Economy.Resources>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_BudgetDataQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceBudgetData>());
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
		CityServiceUpkeepJob jobData = new CityServiceUpkeepJob
		{
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnedVehicleBufType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourcesType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourceConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ResourceConsumer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceObjects = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpkeepDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpkeepData_RO_BufferLookup, ref base.CheckedStateRef),
			m_UpkeepModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UpkeepModifierData_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourceConsumerDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceConsumerData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUsages = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUsage_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Limits = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceBudgetDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ServiceBudgetData_RO_BufferLookup, ref base.CheckedStateRef),
			m_DeliveryTrucks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_QuantityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Quantity_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_PlayerMoney = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_PlayerMoney_RW_ComponentLookup, ref base.CheckedStateRef),
			m_UpdateFrameIndex = updateFrame,
			m_City = m_CitySystem.City,
			m_BudgetDataEntity = m_BudgetDataQuery.GetSingletonEntity(),
			m_RandomSeed = RandomSeed.Next(),
			m_DeliveryTruckSelectData = m_VehicleCapacitySystem.GetDeliveryTruckSelectData(),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_UpkeepGroup, base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.CityServiceUpkeepSystem+CityServiceUpkeepJob`  
- `Game.Simulation.CityServiceUpkeepSystem+TypeHandle`  

