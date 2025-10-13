# Game.Simulation.CompanyUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CompanyUtils
{
    public static System.Int32 GetCommercialMaxFittingWorkers(Game.Prefabs.BuildingData building, Game.Prefabs.BuildingPropertyData properties, System.Int32 level, Game.Companies.ServiceCompanyData serviceData);
    public static System.Int32 GetCompanyMaxFittingWorkers(Unity.Entities.Entity companyEntity, Unity.Entities.Entity buildingEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceCompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCompanyDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.IndustrialProcessData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& industrialProcessDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorCompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorCompanyDatas, Unity.Entities.ComponentLookup`1[[Game.Objects.Attached, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& attacheds, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreaBufs, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries);
    public static System.Int32 GetCompanyMoveAwayChance(Unity.Entities.Entity company, Unity.Entities.Entity companyPrefab, Unity.Entities.Entity property, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Buildings.OfficeProperty, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeProperties, Unity.Entities.ComponentLookup`1[[Game.Prefabs.IndustrialProcessData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& industrialProcessDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Collections.NativeArray<System.Int32> taxRates);
    public static System.Int32 GetExtractorFittingWorkers(System.Single area, System.Single spaceMultiplier, Game.Prefabs.IndustrialProcessData processData);
    public static System.Int32 GetIndustrialAndOfficeFittingWorkers(Game.Prefabs.BuildingData building, Game.Prefabs.BuildingPropertyData properties, System.Int32 level, Game.Prefabs.IndustrialProcessData processData);
}
```


## Methods

- `public static GetCommercialMaxFittingWorkers(Game.Prefabs.BuildingData building, Game.Prefabs.BuildingPropertyData properties, System.Int32 level, Game.Companies.ServiceCompanyData serviceData) : System.Int32`  

```csharp
public static int GetCommercialMaxFittingWorkers(BuildingData building, BuildingPropertyData properties, int level, ServiceCompanyData serviceData)
	{
		return Mathf.CeilToInt(serviceData.m_MaxWorkersPerCell * (float)building.m_LotSize.x * (float)building.m_LotSize.y * (1f + 0.5f * (float)level) * properties.m_SpaceMultiplier);
	}
```

- `public static GetCompanyMaxFittingWorkers(Unity.Entities.Entity companyEntity, Unity.Entities.Entity buildingEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceCompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCompanyDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.IndustrialProcessData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& industrialProcessDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorCompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorCompanyDatas, Unity.Entities.ComponentLookup`1[[Game.Objects.Attached, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& attacheds, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreaBufs, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries) : System.Int32`  

```csharp
public static int GetCompanyMaxFittingWorkers(Entity companyEntity, Entity buildingEntity, ref ComponentLookup<PrefabRef> prefabRefs, ref ComponentLookup<ServiceCompanyData> serviceCompanyDatas, ref ComponentLookup<BuildingData> buildingDatas, ref ComponentLookup<BuildingPropertyData> buildingPropertyDatas, ref ComponentLookup<SpawnableBuildingData> spawnableBuildingDatas, ref ComponentLookup<IndustrialProcessData> industrialProcessDatas, ref ComponentLookup<ExtractorCompanyData> extractorCompanyDatas, ref ComponentLookup<Attached> attacheds, ref BufferLookup<Game.Areas.SubArea> subAreaBufs, ref BufferLookup<InstalledUpgrade> installedUpgrades, ref ComponentLookup<Game.Areas.Lot> lots, ref ComponentLookup<Geometry> geometries)
	{
		Entity entity = prefabRefs[companyEntity];
		Entity entity2 = prefabRefs[buildingEntity];
		int level = 1;
		if (spawnableBuildingDatas.HasComponent(entity2))
		{
			level = spawnableBuildingDatas[entity2].m_Level;
		}
		if (serviceCompanyDatas.HasComponent(entity))
		{
			return GetCommercialMaxFittingWorkers(buildingDatas[entity2], buildingPropertyDatas[entity2], level, serviceCompanyDatas[entity]);
		}
		if (extractorCompanyDatas.HasComponent(entity))
		{
			float area = 0f;
			if (attacheds.HasComponent(buildingEntity))
			{
				area = ExtractorAISystem.GetArea(attacheds[buildingEntity].m_Parent, ref subAreaBufs, ref installedUpgrades, ref lots, ref geometries);
			}
			return math.max(1, GetExtractorFittingWorkers(area, 1f, industrialProcessDatas[entity]));
		}
		if (industrialProcessDatas.HasComponent(entity))
		{
			return GetIndustrialAndOfficeFittingWorkers(buildingDatas[entity2], buildingPropertyDatas[entity2], level, industrialProcessDatas[entity]);
		}
		return 0;
	}
```

- `public static GetCompanyMoveAwayChance(Unity.Entities.Entity company, Unity.Entities.Entity companyPrefab, Unity.Entities.Entity property, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Buildings.OfficeProperty, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeProperties, Unity.Entities.ComponentLookup`1[[Game.Prefabs.IndustrialProcessData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& industrialProcessDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetCompanyMoveAwayChance(Entity company, Entity companyPrefab, Entity property, ref ComponentLookup<ServiceAvailable> serviceAvailables, ref ComponentLookup<OfficeProperty> officeProperties, ref ComponentLookup<IndustrialProcessData> industrialProcessDatas, ref ComponentLookup<WorkProvider> workProviders, NativeArray<int> taxRates)
	{
		int num = 0;
		bool num2 = serviceAvailables.HasComponent(company);
		bool flag = officeProperties.HasComponent(property);
		IndustrialProcessData industrialProcessData = industrialProcessDatas[companyPrefab];
		int num3 = (num2 ? TaxSystem.GetCommercialTaxRate(industrialProcessData.m_Output.m_Resource, taxRates) : ((!flag) ? TaxSystem.GetIndustrialTaxRate(industrialProcessData.m_Output.m_Resource, taxRates) : TaxSystem.GetOfficeTaxRate(industrialProcessData.m_Output.m_Resource, taxRates)));
		num += (num3 - 10) * 5 / 2;
		WorkProvider workProvider = workProviders[company];
		if (workProvider.m_UneducatedNotificationEntity != Entity.Null)
		{
			num += 5;
		}
		if (workProvider.m_EducatedNotificationEntity != Entity.Null)
		{
			num += 20;
		}
		return num;
	}
```

- `public static GetExtractorFittingWorkers(System.Single area, System.Single spaceMultiplier, Game.Prefabs.IndustrialProcessData processData) : System.Int32`  

```csharp
public static int GetExtractorFittingWorkers(float area, float spaceMultiplier, IndustrialProcessData processData)
	{
		return Mathf.CeilToInt(processData.m_MaxWorkersPerCell * area * spaceMultiplier / 2f);
	}
```

- `public static GetIndustrialAndOfficeFittingWorkers(Game.Prefabs.BuildingData building, Game.Prefabs.BuildingPropertyData properties, System.Int32 level, Game.Prefabs.IndustrialProcessData processData) : System.Int32`  

```csharp
public static int GetIndustrialAndOfficeFittingWorkers(BuildingData building, BuildingPropertyData properties, int level, IndustrialProcessData processData)
	{
		return Mathf.CeilToInt(processData.m_MaxWorkersPerCell * (float)building.m_LotSize.x * (float)building.m_LotSize.y * (1f + 0.5f * (float)level) * properties.m_SpaceMultiplier);
	}
```


