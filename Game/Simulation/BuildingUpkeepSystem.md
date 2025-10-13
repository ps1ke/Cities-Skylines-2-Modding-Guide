# Game.Simulation.BuildingUpkeepSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingUpkeepSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Prefabs.ZoneBuiltRequirementSystem m_ZoneBuiltRequirementSystemSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.BuildingUpkeepSystem+UpkeepPayment> m_UpkeepExpenseQueue;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LevelupQueue;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LeveldownQueue;
    private Unity.Entities.EntityQuery m_BuildingPrefabGroup;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Unity.Entities.EntityQuery m_BuildingGroup;
    public System.Boolean debugFastLeveling;
    private Game.Simulation.BuildingUpkeepSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kMaterialUpkeep;

    public BuildingUpkeepSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void DebugLevelDown(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas);
    public System.Void DebugLevelUp(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas);
    public static System.Single GetHeatingMultiplier(System.Single temperature);
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

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Prefabs.ZoneBuiltRequirementSystem m_ZoneBuiltRequirementSystemSystem`  

```csharp
private Game.Prefabs.ZoneBuiltRequirementSystem m_ZoneBuiltRequirementSystemSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
```

- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingUpkeepSystem+UpkeepPayment> m_UpkeepExpenseQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.BuildingUpkeepSystem+UpkeepPayment> m_UpkeepExpenseQueue;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LevelupQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LevelupQueue;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LeveldownQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LeveldownQueue;
```

- `private Unity.Entities.EntityQuery m_BuildingPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `public System.Boolean debugFastLeveling`  

```csharp
public System.Boolean debugFastLeveling;
```

- `private Game.Simulation.BuildingUpkeepSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BuildingUpkeepSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kMaterialUpkeep`  

```csharp
public static readonly System.Int32 kMaterialUpkeep;
```


## Constructors

- `public BuildingUpkeepSystem()`  

```csharp
[Preserve]
	public BuildingUpkeepSystem()
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

- `public DebugLevelDown(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas) : System.Void`  

```csharp
public void DebugLevelDown(Entity building, ComponentLookup<BuildingCondition> conditions, ComponentLookup<SpawnableBuildingData> spawnables, ComponentLookup<PrefabRef> prefabRefs, ComponentLookup<ZoneData> zoneDatas, ComponentLookup<BuildingPropertyData> propertyDatas)
	{
		if (!conditions.HasComponent(building) || !prefabRefs.HasComponent(building))
		{
			return;
		}
		BuildingCondition value = conditions[building];
		Entity prefab = prefabRefs[building].m_Prefab;
		if (spawnables.HasComponent(prefab) && propertyDatas.HasComponent(prefab))
		{
			SpawnableBuildingData spawnableBuildingData = spawnables[prefab];
			if (zoneDatas.HasComponent(spawnableBuildingData.m_ZonePrefab))
			{
				int levelingCost = BuildingUtils.GetLevelingCost(zoneDatas[spawnableBuildingData.m_ZonePrefab].m_AreaType, propertyDatas[prefab], spawnableBuildingData.m_Level, base.EntityManager.GetBuffer<CityModifier>(m_CitySystem.City, isReadOnly: true));
				value.m_Condition = -3 * levelingCost / 2;
				conditions[building] = value;
				m_LeveldownQueue.Enqueue(building);
			}
		}
	}
```

- `public DebugLevelUp(Unity.Entities.Entity building, Unity.Entities.ComponentLookup<Game.Buildings.BuildingCondition> conditions, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnables, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas) : System.Void`  

```csharp
public void DebugLevelUp(Entity building, ComponentLookup<BuildingCondition> conditions, ComponentLookup<SpawnableBuildingData> spawnables, ComponentLookup<PrefabRef> prefabRefs, ComponentLookup<ZoneData> zoneDatas, ComponentLookup<BuildingPropertyData> propertyDatas)
	{
		if (!conditions.HasComponent(building) || !prefabRefs.HasComponent(building))
		{
			return;
		}
		_ = conditions[building];
		Entity prefab = prefabRefs[building].m_Prefab;
		if (spawnables.HasComponent(prefab) && propertyDatas.HasComponent(prefab))
		{
			SpawnableBuildingData spawnableBuildingData = spawnables[prefab];
			if (zoneDatas.HasComponent(spawnableBuildingData.m_ZonePrefab))
			{
				_ = zoneDatas[spawnableBuildingData.m_ZonePrefab];
				m_LevelupQueue.Enqueue(building);
			}
		}
	}
```

- `public static GetHeatingMultiplier(System.Single temperature) : System.Single`  

```csharp
public static float GetHeatingMultiplier(float temperature)
	{
		return math.max(0f, 15f - temperature);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
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
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ZoneBuiltRequirementSystemSystem = base.World.GetOrCreateSystemManaged<ZoneBuiltRequirementSystem>();
		m_ZoneSearchSystem = base.World.GetOrCreateSystemManaged<Game.Zones.SearchSystem>();
		m_ElectricityRoadConnectionGraphSystem = base.World.GetOrCreateSystemManaged<ElectricityRoadConnectionGraphSystem>();
		m_WaterPipeRoadConnectionGraphSystem = base.World.GetOrCreateSystemManaged<WaterPipeRoadConnectionGraphSystem>();
		m_UpkeepExpenseQueue = new NativeQueue<UpkeepPayment>(Allocator.Persistent);
		m_BuildingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		m_LevelupQueue = new NativeQueue<Entity>(Allocator.Persistent);
		m_LeveldownQueue = new NativeQueue<Entity>(Allocator.Persistent);
		m_BuildingGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<BuildingCondition>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			Any = new ComponentType[0],
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Abandoned>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_BuildingPrefabGroup = GetEntityQuery(ComponentType.ReadOnly<BuildingData>(), ComponentType.ReadOnly<BuildingSpawnGroupData>(), ComponentType.ReadOnly<PrefabData>());
		RequireForUpdate(m_BuildingGroup);
		RequireForUpdate(m_BuildingSettingsQuery);
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
		base.OnDestroy();
		m_UpkeepExpenseQueue.Dispose();
		m_LevelupQueue.Dispose();
		m_LeveldownQueue.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		BuildingConfigurationData singleton = m_BuildingSettingsQuery.GetSingleton<BuildingConfigurationData>();
		BuildingUpkeepJob jobData = new BuildingUpkeepJob
		{
			m_ConditionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_BuildingCondition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_ConsumptionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Availabilities = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifierBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_SignatureDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Abandoned = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Destroyed = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_DeliveryTrucks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_BuildingConfigurationData = singleton,
			m_UpdateFrameIndex = updateFrame,
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_UpkeepExpenseQueue = m_UpkeepExpenseQueue.AsParallelWriter(),
			m_LevelupQueue = m_LevelupQueue.AsParallelWriter(),
			m_LevelDownQueue = m_LeveldownQueue.AsParallelWriter(),
			m_DebugFastLeveling = debugFastLeveling,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_TemperatureUpkeep = GetHeatingMultiplier(m_ClimateSystem.temperature)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_BuildingGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
		JobHandle outJobHandle;
		JobHandle dependencies;
		JobHandle deps;
		LevelupJob jobData2 = new LevelupJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_SpawnableBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingSpawnGroupType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingSpawnGroupData_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ValidAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_ValidArea_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OfficeBuilding = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OfficeBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RO_BufferLookup, ref base.CheckedStateRef),
			m_BuildingConfigurationData = singleton,
			m_SpawnableBuildingChunks = m_BuildingPrefabGroup.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_ZoneSearchTree = m_ZoneSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_RandomSeed = RandomSeed.Next(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_LevelupQueue = m_LevelupQueue,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer(),
			m_ZoneBuiltLevelQueue = m_ZoneBuiltRequirementSystemSystem.GetZoneBuiltLevelQueue(out deps)
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, JobUtils.CombineDependencies(base.Dependency, outJobHandle, dependencies, deps));
		m_ZoneSearchSystem.AddSearchTreeReader(base.Dependency);
		m_ZoneBuiltRequirementSystemSystem.AddWriter(base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		JobHandle deps2;
		JobHandle deps3;
		LeveldownJob jobData3 = new LeveldownJob
		{
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MailProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OfficeBuilding = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OfficeBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer(),
			m_CrimeProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CrimeProducer_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RW_BufferLookup, ref base.CheckedStateRef),
			m_BuildingConfigurationData = singleton,
			m_LeveldownQueue = m_LeveldownQueue,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
			m_UpdatedElectricityRoadEdges = m_ElectricityRoadConnectionGraphSystem.GetEdgeUpdateQueue(out deps2),
			m_UpdatedWaterPipeRoadEdges = m_WaterPipeRoadConnectionGraphSystem.GetEdgeUpdateQueue(out deps3),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_SimulationFrame = m_SimulationSystem.frameIndex
		};
		base.Dependency = IJobExtensions.Schedule(jobData3, JobHandle.CombineDependencies(base.Dependency, deps2, deps3));
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_ElectricityRoadConnectionGraphSystem.AddQueueWriter(base.Dependency);
		m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		UpkeepPaymentJob jobData4 = new UpkeepPaymentJob
		{
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RW_BufferLookup, ref base.CheckedStateRef),
			m_UpkeepExpenseQueue = m_UpkeepExpenseQueue
		};
		base.Dependency = IJobExtensions.Schedule(jobData4, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.BuildingUpkeepSystem+UpkeepPayment`  
- `Game.Simulation.BuildingUpkeepSystem+BuildingUpkeepJob`  
- `Game.Simulation.BuildingUpkeepSystem+UpkeepPaymentJob`  
- `Game.Simulation.BuildingUpkeepSystem+LeveldownJob`  
- `Game.Simulation.BuildingUpkeepSystem+LevelupJob`  
- `Game.Simulation.BuildingUpkeepSystem+TypeHandle`  

