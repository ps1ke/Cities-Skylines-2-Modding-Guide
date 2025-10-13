# Game.Simulation.ZoneSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneSpawnSystem : Game.GameSystemBase
{
    private System.Boolean <debugFastSpawn>k__BackingField;
    private Game.Prefabs.ZoneSystem m_ZoneSystem;
    private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.GroundPollutionSystem m_PollutionSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Zones.SearchSystem m_SearchSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_LotQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_ProcessQuery;
    private Unity.Entities.EntityQuery m_BuildingConfigurationQuery;
    private Unity.Entities.EntityArchetype m_DefinitionArchetype;
    private Game.Simulation.ZoneSpawnSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1944910157_0;

    public System.Boolean debugFastSpawn { get; set; }

    public ZoneSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <debugFastSpawn>k__BackingField`  

```csharp
private System.Boolean <debugFastSpawn>k__BackingField;
```

- `private Game.Prefabs.ZoneSystem m_ZoneSystem`  

```csharp
private Game.Prefabs.ZoneSystem m_ZoneSystem;
```

- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  

```csharp
private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
```

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_PollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_PollutionSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Zones.SearchSystem m_SearchSystem`  

```csharp
private Game.Zones.SearchSystem m_SearchSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_LotQuery`  

```csharp
private Unity.Entities.EntityQuery m_LotQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingConfigurationQuery;
```

- `private Unity.Entities.EntityArchetype m_DefinitionArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DefinitionArchetype;
```

- `private Game.Simulation.ZoneSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ZoneSpawnSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1944910157_0`  

```csharp
private Unity.Entities.EntityQuery __query_1944910157_0;
```


## Properties

- `public System.Boolean debugFastSpawn { get; set }`  

```csharp
public System.Boolean debugFastSpawn { get; set; }
```


## Constructors

- `public ZoneSpawnSystem()`  

```csharp
[Preserve]
	public ZoneSpawnSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<ZonePreferenceData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1944910157_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
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
		return 13;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ZoneSystem = base.World.GetOrCreateSystemManaged<ZoneSystem>();
		m_ResidentialDemandSystem = base.World.GetOrCreateSystemManaged<ResidentialDemandSystem>();
		m_CommercialDemandSystem = base.World.GetOrCreateSystemManaged<CommercialDemandSystem>();
		m_IndustrialDemandSystem = base.World.GetOrCreateSystemManaged<IndustrialDemandSystem>();
		m_PollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<Game.Zones.SearchSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_LotQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Block>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<CurvePosition>(),
				ComponentType.ReadOnly<VacantLot>()
			},
			Any = new ComponentType[0],
			None = new ComponentType[2]
			{
				ComponentType.ReadWrite<Temp>(),
				ComponentType.ReadWrite<Deleted>()
			}
		});
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingData>(), ComponentType.ReadOnly<SpawnableBuildingData>(), ComponentType.ReadOnly<BuildingSpawnGroupData>(), ComponentType.ReadOnly<PrefabData>());
		m_DefinitionArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<CreationDefinition>(), ComponentType.ReadWrite<ObjectDefinition>(), ComponentType.ReadWrite<Updated>(), ComponentType.ReadWrite<Deleted>());
		m_ProcessQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>());
		m_BuildingConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		RequireForUpdate(m_LotQuery);
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
		RandomSeed.Next().GetRandom(0);
		bool flag = debugFastSpawn || (m_ResidentialDemandSystem.buildingDemand.x + m_ResidentialDemandSystem.buildingDemand.y + m_ResidentialDemandSystem.buildingDemand.z) / 3 > 0;
		bool flag2 = debugFastSpawn || m_CommercialDemandSystem.buildingDemand > 0;
		bool flag3 = debugFastSpawn || (m_IndustrialDemandSystem.industrialBuildingDemand + m_IndustrialDemandSystem.officeBuildingDemand) / 2 > 0;
		bool flag4 = debugFastSpawn || m_IndustrialDemandSystem.storageBuildingDemand > 0;
		NativeQueue<SpawnLocation> residential = new NativeQueue<SpawnLocation>(Allocator.TempJob);
		NativeQueue<SpawnLocation> commercial = new NativeQueue<SpawnLocation>(Allocator.TempJob);
		NativeQueue<SpawnLocation> industrial = new NativeQueue<SpawnLocation>(Allocator.TempJob);
		JobHandle outJobHandle;
		JobHandle deps;
		JobHandle deps2;
		JobHandle deps3;
		JobHandle outJobHandle2;
		JobHandle dependencies;
		EvaluateSpawnAreas jobData = new EvaluateSpawnAreas
		{
			m_BuildingChunks = m_BuildingQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_ZonePrefabs = m_ZoneSystem.GetPrefabs(),
			m_Preferences = __query_1944910157_0.GetSingleton<ZonePreferenceData>(),
			m_SpawnResidential = (flag ? 1 : 0),
			m_SpawnCommercial = (flag2 ? 1 : 0),
			m_SpawnIndustrial = (flag3 ? 1 : 0),
			m_SpawnStorage = (flag4 ? 1 : 0),
			m_MinDemand = ((!debugFastSpawn) ? 1 : 0),
			m_ResidentialDemands = m_ResidentialDemandSystem.buildingDemand,
			m_CommercialBuildingDemands = m_CommercialDemandSystem.GetBuildingDemands(out deps),
			m_IndustrialDemands = m_IndustrialDemandSystem.GetBuildingDemands(out deps2),
			m_StorageDemands = m_IndustrialDemandSystem.GetStorageBuildingDemands(out deps3),
			m_RandomSeed = RandomSeed.Next(),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_Block_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurvePositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_CurvePosition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VacantLotType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Zones_VacantLot_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnableBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingSpawnGroupType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingSpawnGroupData_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_WarehouseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WarehouseData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZonePropertiesDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZonePropertiesData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Availabilities = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
			m_LandValues = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Processes = m_ProcessQuery.ToComponentDataListAsync<IndustrialProcessData>(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
			m_ProcessEstimates = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_ProcessEstimate_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_PollutionMap = m_PollutionSystem.GetMap(readOnly: true, out dependencies),
			m_Residential = residential.AsParallelWriter(),
			m_Commercial = commercial.AsParallelWriter(),
			m_Industrial = industrial.AsParallelWriter()
		};
		JobHandle dependencies2;
		SpawnBuildingJob jobData2 = new SpawnBuildingJob
		{
			m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ValidAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_ValidArea_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubAreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubAreaNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabPlaceholderElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_DefinitionArchetype = m_DefinitionArchetype,
			m_RandomSeed = RandomSeed.Next(),
			m_LefthandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_ZoneSearchTree = m_SearchSystem.GetSearchTree(readOnly: true, out dependencies2),
			m_BuildingConfigurationData = m_BuildingConfigurationQuery.GetSingleton<BuildingConfigurationData>(),
			m_Residential = residential,
			m_Commercial = commercial,
			m_Industrial = industrial,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_LotQuery, JobUtils.CombineDependencies(outJobHandle, deps, deps2, deps3, dependencies, base.Dependency, outJobHandle2));
		JobHandle jobHandle2 = IJobParallelForExtensions.Schedule(jobData2, 3, 1, JobHandle.CombineDependencies(jobHandle, dependencies2));
		m_ResourceSystem.AddPrefabsReader(jobHandle);
		m_PollutionSystem.AddReader(jobHandle);
		m_CommercialDemandSystem.AddReader(jobHandle);
		m_IndustrialDemandSystem.AddReader(jobHandle);
		residential.Dispose(jobHandle2);
		commercial.Dispose(jobHandle2);
		industrial.Dispose(jobHandle2);
		m_ZoneSystem.AddPrefabsReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle2);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		m_SearchSystem.AddSearchTreeReader(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.ZoneSpawnSystem+SpawnLocation`  
- `Game.Simulation.ZoneSpawnSystem+EvaluateSpawnAreas`  
- `Game.Simulation.ZoneSpawnSystem+SpawnBuildingJob`  
- `Game.Simulation.ZoneSpawnSystem+TypeHandle`  

