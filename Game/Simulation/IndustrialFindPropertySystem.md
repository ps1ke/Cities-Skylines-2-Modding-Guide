# Game.Simulation.IndustrialFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IndustrialFindPropertySystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Unity.Entities.EntityQuery m_IndustryQuery;
    private Unity.Entities.EntityQuery m_ExtractorQuery;
    private Unity.Entities.EntityQuery m_FreePropertyQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_ZonePreferenceQuery;
    private Unity.Entities.EntityQuery m_FreeExtractorQuery;
    private Unity.Entities.EntityQuery m_CompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Game.Simulation.IndustrialFindPropertySystem+TypeHandle __TypeHandle;

    public IndustrialFindPropertySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> propertiesOnMarket, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> workplaceDatas, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.EconomyParameterData economyParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, System.Boolean storage);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  

```csharp
private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Unity.Entities.EntityQuery m_IndustryQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustryQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorQuery;
```

- `private Unity.Entities.EntityQuery m_FreePropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreePropertyQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ZonePreferenceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ZonePreferenceQuery;
```

- `private Unity.Entities.EntityQuery m_FreeExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreeExtractorQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Game.Simulation.IndustrialFindPropertySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.IndustrialFindPropertySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IndustrialFindPropertySystem()`  

```csharp
[Preserve]
	public IndustrialFindPropertySystem()
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

- `public static Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> propertiesOnMarket, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> workplaceDatas, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.EconomyParameterData economyParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, System.Boolean storage) : System.Single`  

```csharp
public static float Evaluate(Entity company, Entity property, ref IndustrialProcessData process, ref PropertySeeker propertySeeker, ComponentLookup<Building> buildings, ComponentLookup<PropertyOnMarket> propertiesOnMarket, ComponentLookup<PrefabRef> prefabFromEntity, ComponentLookup<BuildingData> buildingDatas, ComponentLookup<SpawnableBuildingData> spawnableDatas, ComponentLookup<WorkplaceData> workplaceDatas, ComponentLookup<LandValue> landValues, BufferLookup<ResourceAvailability> availabilities, EconomyParameterData economyParameters, ResourcePrefabs resourcePrefabs, ComponentLookup<ResourceData> resourceDatas, ComponentLookup<BuildingPropertyData> propertyDatas, bool storage)
	{
		if (buildings.HasComponent(property) && availabilities.HasBuffer(buildings[property].m_RoadEdge))
		{
			Building building = buildings[property];
			Entity prefab = prefabFromEntity[property].m_Prefab;
			Entity prefab2 = prefabFromEntity[company].m_Prefab;
			float num = 0f;
			if (storage)
			{
				DynamicBuffer<ResourceAvailability> availabilities2 = availabilities[building.m_RoadEdge];
				float weight = EconomyUtils.GetWeight(process.m_Output.m_Resource, resourcePrefabs, ref resourceDatas);
				num += 50f * weight * (float)process.m_Output.m_Amount * NetUtils.GetAvailability(availabilities2, EconomyUtils.GetAvailableResourceSupply(process.m_Output.m_Resource), building.m_CurvePosition);
			}
			else
			{
				if (!workplaceDatas.HasComponent(prefab2))
				{
					return -1f;
				}
				num += 500f;
				DynamicBuffer<ResourceAvailability> availabilities3 = availabilities[building.m_RoadEdge];
				num += 10f * NetUtils.GetAvailability(availabilities3, AvailableResource.UneducatedCitizens, building.m_CurvePosition);
				if (process.m_Input1.m_Resource != Resource.NoResource)
				{
					float weight2 = EconomyUtils.GetWeight(process.m_Input1.m_Resource, resourcePrefabs, ref resourceDatas);
					num += 50f * weight2 * (float)process.m_Input1.m_Amount * NetUtils.GetAvailability(availabilities3, EconomyUtils.GetAvailableResourceSupply(process.m_Input1.m_Resource), building.m_CurvePosition);
				}
				if (process.m_Input2.m_Resource != Resource.NoResource)
				{
					float weight3 = EconomyUtils.GetWeight(process.m_Input2.m_Resource, resourcePrefabs, ref resourceDatas);
					num += 50f * weight3 * (float)process.m_Input2.m_Amount * NetUtils.GetAvailability(availabilities3, EconomyUtils.GetAvailableResourceSupply(process.m_Input2.m_Resource), building.m_CurvePosition);
				}
			}
			float landValue = landValues[building.m_RoadEdge].m_LandValue;
			float num2 = 1f;
			int num3 = 1;
			if (spawnableDatas.TryGetComponent(property, out var componentData))
			{
				num3 = componentData.m_Level;
			}
			float num4 = propertyDatas[prefab].m_SpaceMultiplier * (1f + 0.5f * (float)num3);
			if (!storage)
			{
				num2 = num4 * process.m_MaxWorkersPerCell;
				if (EconomyUtils.GetWeight(process.m_Output.m_Resource, resourcePrefabs, ref resourceDatas) == 0f)
				{
					num2 *= 3f;
				}
			}
			num -= landValue / num2;
			return 250f + num;
		}
		return 0f;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_PropertyProcessingSystem = base.World.GetOrCreateSystemManaged<PropertyProcessingSystem>();
		m_IndustrialDemandSystem = base.World.GetOrCreateSystemManaged<IndustrialDemandSystem>();
		m_CountCompanyDataSystem = base.World.GetOrCreateSystemManaged<CountCompanyDataSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_CompanyPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialCompanyData>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_ExtractorParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ExtractorParameterData>());
		m_IndustryQuery = GetEntityQuery(ComponentType.ReadWrite<IndustrialCompany>(), ComponentType.ReadWrite<CompanyData>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<ServiceAvailable>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Created>(), ComponentType.Exclude<Game.Companies.ExtractorCompany>());
		m_ExtractorQuery = GetEntityQuery(ComponentType.ReadWrite<IndustrialCompany>(), ComponentType.ReadWrite<CompanyData>(), ComponentType.ReadOnly<Game.Companies.ExtractorCompany>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<ServiceAvailable>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Created>());
		m_FreeExtractorQuery = GetEntityQuery(ComponentType.ReadWrite<PropertyOnMarket>(), ComponentType.ReadWrite<ExtractorProperty>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Abandoned>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Condemned>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_FreePropertyQuery = GetEntityQuery(ComponentType.ReadWrite<PropertyOnMarket>(), ComponentType.ReadWrite<IndustrialProperty>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<ExtractorProperty>(), ComponentType.Exclude<Abandoned>(), ComponentType.Exclude<Condemned>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_ZonePreferenceQuery = GetEntityQuery(ComponentType.ReadOnly<ZonePreferenceData>());
		RequireAnyForUpdate(m_IndustryQuery, m_ExtractorQuery);
		RequireForUpdate(m_EconomyParameterQuery);
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
		JobHandle deps = default(JobHandle);
		if (!m_IndustryQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			PropertyUtils.CompanyFindPropertyJob jobData = new PropertyUtils.CompanyFindPropertyJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PropertySeekerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_PropertySeeker_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CompanyDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_CompanyData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StorageCompanyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FreePropertyEntities = m_FreePropertyQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_PropertyPrefabs = m_FreePropertyQuery.ToComponentDataListAsync<PrefabRef>(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
				m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertiesOnMarket = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyOnMarket_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Availabilities = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
				m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LandValues = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WorkplaceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommercialCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CommercialCompany_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Signatures = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Signature_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
				m_ZonePreferences = m_ZonePreferenceQuery.GetSingleton<ZonePreferenceData>(),
				m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
				m_Commercial = false,
				m_RentActionQueue = m_PropertyProcessingSystem.GetRentActionQueue(out deps).AsParallelWriter(),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_IndustryQuery, JobUtils.CombineDependencies(outJobHandle, outJobHandle2, deps, base.Dependency));
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
			m_ResourceSystem.AddPrefabsReader(base.Dependency);
			m_PropertyProcessingSystem.AddWriter(base.Dependency);
		}
		JobHandle outJobHandle3;
		JobHandle outJobHandle4;
		JobHandle outJobHandle5;
		JobHandle deps2;
		JobHandle deps3;
		PropertyUtils.ExtractorFindCompanyJob jobData2 = new PropertyUtils.ExtractorFindCompanyJob
		{
			m_Entities = m_FreeExtractorQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle3),
			m_ExtractorCompanyEntities = m_ExtractorQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle4),
			m_CompanyPrefabs = m_CompanyPrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle5),
			m_Attached = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorAreas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Extractor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Geometries = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Lots = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Processes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Properties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_WorkplaceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_Productions = m_CountCompanyDataSystem.GetProduction(out deps2),
			m_Consumptions = m_IndustrialDemandSystem.GetConsumption(out deps3),
			m_ExtractorParameters = m_ExtractorParameterQuery.GetSingleton<ExtractorParameterData>(),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_RentActionQueue = m_PropertyProcessingSystem.GetRentActionQueue(out deps),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
			m_AverageTemperature = m_ClimateSystem.averageTemperature
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, JobUtils.CombineDependencies(base.Dependency, outJobHandle3, outJobHandle4, outJobHandle5, deps2, deps3, deps));
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
		m_IndustrialDemandSystem.AddReader(base.Dependency);
		m_CountCompanyDataSystem.AddReader(base.Dependency);
		m_PropertyProcessingSystem.AddWriter(base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.IndustrialFindPropertySystem+TypeHandle`  

