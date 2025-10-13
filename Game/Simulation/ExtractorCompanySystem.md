# Game.Simulation.ExtractorCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ExtractorCompanySystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem;
    private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Game.Simulation.ExtractorCompanySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1012523227_0;
    private Unity.Entities.EntityQuery __query_1012523227_1;

    public ExtractorCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Boolean GetBestConcentration(Game.Economy.Resource resource, Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Single& concentration, System.Single& size);
    private static System.Void GetBestConcentration(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, System.Boolean requireNaturalResource, System.Single& concentration, System.Single& size);
    public static System.Single GetEffectiveConcentration(Game.Prefabs.ExtractorParameterData extractorParameters, Game.Areas.MapFeature feature, System.Single concentration);
    public static Game.Areas.MapFeature GetRequiredMapFeature(Game.Economy.Resource output, Unity.Entities.Entity lotPrefab, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
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

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem`  

```csharp
private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem;
```

- `private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem`  

```csharp
private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem;
```

- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  

```csharp
private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Game.Simulation.ExtractorCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ExtractorCompanySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1012523227_0`  

```csharp
private Unity.Entities.EntityQuery __query_1012523227_0;
```

- `private Unity.Entities.EntityQuery __query_1012523227_1`  

```csharp
private Unity.Entities.EntityQuery __query_1012523227_1;
```


## Constructors

- `public ExtractorCompanySystem()`  

```csharp
[Preserve]
	public ExtractorCompanySystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<EconomyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1012523227_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<ExtractorParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1012523227_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public static GetBestConcentration(Game.Economy.Resource resource, Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Single& concentration, System.Single& size) : System.Boolean`  

```csharp
private static void GetBestConcentration(DynamicBuffer<Game.Areas.SubArea> subAreas, ref ComponentLookup<Extractor> extractors, ref ComponentLookup<Geometry> geometries, ref ComponentLookup<PrefabRef> prefabs, ref ComponentLookup<ExtractorAreaData> extractorDatas, ExtractorParameterData extractorParameters, bool requireNaturalResource, ref float concentration, ref float size)
	{
		for (int i = 0; i < subAreas.Length; i++)
		{
			Entity area = subAreas[i].m_Area;
			if (extractors.TryGetComponent(area, out var componentData) && geometries.TryGetComponent(area, out var componentData2) && prefabs.TryGetComponent(area, out var componentData3) && extractorDatas.TryGetComponent(componentData3.m_Prefab, out var componentData4))
			{
				if (requireNaturalResource && componentData4.m_RequireNaturalResource)
				{
					float effectiveConcentration = GetEffectiveConcentration(extractorParameters, componentData4.m_MapFeature, componentData.m_MaxConcentration);
					effectiveConcentration = math.min(1f, effectiveConcentration);
					concentration += effectiveConcentration * componentData2.m_SurfaceArea;
					size += componentData2.m_SurfaceArea;
				}
				else
				{
					concentration += componentData2.m_SurfaceArea;
					size += componentData2.m_SurfaceArea;
				}
			}
		}
	}
```

- `private static GetBestConcentration(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, System.Boolean requireNaturalResource, System.Single& concentration, System.Single& size) : System.Void`  

```csharp
private static void GetBestConcentration(DynamicBuffer<Game.Areas.SubArea> subAreas, ref ComponentLookup<Extractor> extractors, ref ComponentLookup<Geometry> geometries, ref ComponentLookup<PrefabRef> prefabs, ref ComponentLookup<ExtractorAreaData> extractorDatas, ExtractorParameterData extractorParameters, bool requireNaturalResource, ref float concentration, ref float size)
	{
		for (int i = 0; i < subAreas.Length; i++)
		{
			Entity area = subAreas[i].m_Area;
			if (extractors.TryGetComponent(area, out var componentData) && geometries.TryGetComponent(area, out var componentData2) && prefabs.TryGetComponent(area, out var componentData3) && extractorDatas.TryGetComponent(componentData3.m_Prefab, out var componentData4))
			{
				if (requireNaturalResource && componentData4.m_RequireNaturalResource)
				{
					float effectiveConcentration = GetEffectiveConcentration(extractorParameters, componentData4.m_MapFeature, componentData.m_MaxConcentration);
					effectiveConcentration = math.min(1f, effectiveConcentration);
					concentration += effectiveConcentration * componentData2.m_SurfaceArea;
					size += componentData2.m_SurfaceArea;
				}
				else
				{
					concentration += componentData2.m_SurfaceArea;
					size += componentData2.m_SurfaceArea;
				}
			}
		}
	}
```

- `public static GetEffectiveConcentration(Game.Prefabs.ExtractorParameterData extractorParameters, Game.Areas.MapFeature feature, System.Single concentration) : System.Single`  

```csharp
public static float GetEffectiveConcentration(ExtractorParameterData extractorParameters, MapFeature feature, float concentration)
	{
		return math.min(1f, concentration / feature switch
		{
			MapFeature.Oil => extractorParameters.m_FullOil, 
			MapFeature.FertileLand => extractorParameters.m_FullFertility, 
			MapFeature.Fish => extractorParameters.m_FullFish, 
			MapFeature.Ore => extractorParameters.m_FullOre, 
			_ => 1f, 
		});
	}
```

- `public static GetRequiredMapFeature(Game.Economy.Resource output, Unity.Entities.Entity lotPrefab, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas) : Game.Areas.MapFeature`  

```csharp
public static MapFeature GetRequiredMapFeature(Resource output, Entity lotPrefab, ResourcePrefabs resourcePrefabs, ComponentLookup<ResourceData> resourceDatas, ComponentLookup<ExtractorAreaData> extractorAreaDatas)
	{
		if (resourceDatas.TryGetComponent(resourcePrefabs[output], out var componentData) && componentData.m_RequireNaturalResource && extractorAreaDatas.TryGetComponent(lotPrefab, out var componentData2) && componentData2.m_RequireNaturalResource)
		{
			return componentData2.m_MapFeature;
		}
		return MapFeature.None;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (EconomyUtils.kCompanyUpdatesPerDay * 16);
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
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_VehicleCapacitySystem = base.World.GetOrCreateSystemManaged<VehicleCapacitySystem>();
		m_ProcessingCompanySystem = base.World.GetOrCreateSystemManaged<ProcessingCompanySystem>();
		m_ProductionSpecializationSystem = base.World.GetOrCreateSystemManaged<ProductionSpecializationSystem>();
		m_AchievementTriggerSystem = base.World.GetOrCreateSystemManaged<AchievementTriggerSystem>();
		m_CitySystem = base.World.GetExistingSystemManaged<CitySystem>();
		m_CompanyGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.ExtractorCompany>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadWrite<Resources>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<WorkProvider>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<CompanyData>(), ComponentType.ReadWrite<Employee>());
		RequireForUpdate(m_CompanyGroup);
		RequireForUpdate<EconomyParameterData>();
		RequireForUpdate<ExtractorParameterData>();
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, EconomyUtils.kCompanyUpdatesPerDay, 16);
		IAchievement achievement;
		IAchievement achievement2;
		JobHandle dependencies;
		JobHandle deps;
		ExtractorJob jobData = new ExtractorJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CompanyResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ExtractorAreas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Extractor_RW_ComponentLookup, ref base.CheckedStateRef),
			m_GeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EmployeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_TaxPayerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_TaxPayer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageLimitDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingEfficiencies = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RW_BufferLookup, ref base.CheckedStateRef),
			m_WorkplaceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Attached = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorAreaDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubRouteBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_SubRoute_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteWaypointBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_Connecteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorFacilityDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableObjectDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ResourceConnection_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_EconomyParameters = __query_1012523227_0.GetSingleton<EconomyParameterData>(),
			m_ExtractorParameters = __query_1012523227_1.GetSingleton<ExtractorParameterData>(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_City = m_CitySystem.City,
			m_RandomSeed = RandomSeed.Next(),
			m_UpdateFrameIndex = updateFrame,
			m_ShouldCheckOffshoreOilProduce = (PlatformManager.instance.achievementsEnabled && PlatformManager.instance.GetAchievement(Game.Achievements.Achievements.ADifferentPlatformer, out achievement) && !achievement.achieved),
			m_ShouldCheckProducedFish = (PlatformManager.instance.achievementsEnabled && PlatformManager.instance.GetAchievement(Game.Achievements.Achievements.HowMuchIsTheFish, out achievement2) && !achievement2.achieved),
			m_OffshoreOilProduceCounter = m_AchievementTriggerSystem.m_OffshoreOilProduceCounter.ToConcurrent(),
			m_ProducedFishCounter = m_AchievementTriggerSystem.m_ProducedFishCounter.ToConcurrent(),
			m_ProducedResources = m_ProcessingCompanySystem.GetProducedResourcesArray(out dependencies),
			m_ProductionQueue = m_ProductionSpecializationSystem.GetQueue(out deps).AsParallelWriter(),
			m_DeliveryTruckSelectData = m_VehicleCapacitySystem.GetDeliveryTruckSelectData()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CompanyGroup, JobHandle.CombineDependencies(dependencies, deps, base.Dependency));
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_TaxSystem.AddReader(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ExtractorCompanySystem+ExtractorJob`  
- `Game.Simulation.ExtractorCompanySystem+TypeHandle`  

