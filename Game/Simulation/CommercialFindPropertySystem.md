# Game.Simulation.CommercialFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CommercialFindPropertySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CommerceQuery;
    private Unity.Entities.EntityQuery m_FreePropertyQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_ZonePreferenceQuery;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CommercialFindPropertySystem+TypeHandle __TypeHandle;

    public CommercialFindPropertySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterBuffers, Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> companies, Game.Prefabs.ZonePreferenceData& preferences);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CommerceQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommerceQuery;
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

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  

```csharp
private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.CommercialFindPropertySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CommercialFindPropertySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CommercialFindPropertySystem()`  

```csharp
[Preserve]
	public CommercialFindPropertySystem()
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

- `public static Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterBuffers, Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> companies, Game.Prefabs.ZonePreferenceData& preferences) : System.Single`  

```csharp
public static float Evaluate(Entity company, Entity property, ref ServiceCompanyData service, ref IndustrialProcessData process, ref PropertySeeker propertySeeker, ComponentLookup<Building> buildings, ComponentLookup<PrefabRef> prefabFromEntity, ComponentLookup<BuildingData> buildingDatas, BufferLookup<ResourceAvailability> availabilities, ComponentLookup<LandValue> landValues, ResourcePrefabs resourcePrefabs, ComponentLookup<ResourceData> resourceDatas, ComponentLookup<BuildingPropertyData> propertyDatas, ComponentLookup<SpawnableBuildingData> spawnableDatas, BufferLookup<Renter> renterBuffers, ComponentLookup<CommercialCompany> companies, ref ZonePreferenceData preferences)
	{
		if (buildings.HasComponent(property))
		{
			Building building = buildings[property];
			Entity prefab = prefabFromEntity[property].m_Prefab;
			_ = buildingDatas[prefab];
			BuildingPropertyData buildingPropertyData = propertyDatas[prefab];
			DynamicBuffer<Renter> dynamicBuffer = renterBuffers[property];
			for (int i = 0; i < dynamicBuffer.Length; i++)
			{
				if (companies.HasComponent(dynamicBuffer[i].m_Renter))
				{
					return -1f;
				}
			}
			float num = 500f;
			if (availabilities.HasBuffer(building.m_RoadEdge))
			{
				DynamicBuffer<ResourceAvailability> availabilities2 = availabilities[building.m_RoadEdge];
				float num2 = 0f;
				if (landValues.HasComponent(building.m_RoadEdge))
				{
					num2 = landValues[building.m_RoadEdge].m_LandValue;
				}
				float spaceMultiplier = buildingPropertyData.m_SpaceMultiplier;
				int level = spawnableDatas[prefab].m_Level;
				num = ZoneEvaluationUtils.GetCommercialScore(availabilities2, building.m_CurvePosition, ref preferences, num2 / (spaceMultiplier * (1f + 0.5f * (float)level) * service.m_MaxWorkersPerCell), process.m_Output.m_Resource == Resource.Lodging);
				AvailableResource availableResourceSupply = EconomyUtils.GetAvailableResourceSupply(process.m_Input1.m_Resource);
				if (availableResourceSupply != AvailableResource.Count)
				{
					float weight = EconomyUtils.GetWeight(process.m_Input1.m_Resource, resourcePrefabs, ref resourceDatas);
					float marketPrice = EconomyUtils.GetMarketPrice(process.m_Output.m_Resource, resourcePrefabs, ref resourceDatas);
					float num3 = weight * (float)process.m_Input1.m_Amount / ((float)process.m_Output.m_Amount * marketPrice);
					num -= 200f * num3 / math.max(1f, NetUtils.GetAvailability(availabilities2, availableResourceSupply, building.m_CurvePosition));
				}
			}
			return num;
		}
		return -1f;
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
		m_CommerceQuery = GetEntityQuery(ComponentType.ReadWrite<ServiceAvailable>(), ComponentType.ReadWrite<ResourceSeller>(), ComponentType.ReadWrite<CompanyData>(), ComponentType.ReadWrite<PropertySeeker>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Created>());
		m_FreePropertyQuery = GetEntityQuery(ComponentType.ReadWrite<PropertyOnMarket>(), ComponentType.ReadWrite<CommercialProperty>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Abandoned>(), ComponentType.Exclude<Condemned>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_ZonePreferenceQuery = GetEntityQuery(ComponentType.ReadOnly<ZonePreferenceData>());
		RequireForUpdate(m_CommerceQuery);
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
		if (m_CommerceQuery.CalculateEntityCount() > 0)
		{
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			JobHandle deps;
			PropertyUtils.CompanyFindPropertyJob jobData = new PropertyUtils.CompanyFindPropertyJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentTypeHandle, ref base.CheckedStateRef),
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
				m_Commercial = true,
				m_RentActionQueue = m_PropertyProcessingSystem.GetRentActionQueue(out deps).AsParallelWriter(),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CommerceQuery, JobUtils.CombineDependencies(outJobHandle, outJobHandle2, deps, base.Dependency));
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
			m_ResourceSystem.AddPrefabsReader(base.Dependency);
			m_PropertyProcessingSystem.AddWriter(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.CommercialFindPropertySystem+TypeHandle`  

