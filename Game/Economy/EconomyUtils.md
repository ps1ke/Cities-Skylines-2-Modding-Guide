# Game.Economy.EconomyUtils

**Assembly:** `Game`  
**Namespace:** `Game.Economy`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class EconomyUtils
{
    public static readonly System.Int32 kCompanyUpdatesPerDay;
    public static readonly System.Int32 ResourceCount;

    public EconomyUtils();

    public static System.Int32 AddResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources);
    public static System.Void AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> from, Unity.Entities.DynamicBuffer<Game.Economy.Resources> to);
    public static Unity.Mathematics.float3 BuildPseudoTradeCost(System.Single distance, Game.Prefabs.IndustrialProcessData process, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs);
    public static Game.Companies.Workplaces CalculateNumberOfWorkplaces(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel);
    public static System.Int32 CalculateTotalWage(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.EconomyParameterData& econParams);
    public static System.Int32 CalculateTotalWage(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel, Game.Prefabs.EconomyParameterData econParams);
    public static System.Int32 CountResources(Game.Economy.Resource resource);
    public static Game.Economy.Resource GetAllResources();
    public static Game.Net.AvailableResource GetAvailableResourceSupply(Game.Economy.Resource resource);
    public static System.Single GetAverageWorkforce(System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel);
    public static System.Single GetAverageWorkforce(Game.Companies.Workplaces workplaces);
    public static System.Single GetAverageWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees);
    public static System.Int32 GetCompanyMaxProfitPerDay(Game.Companies.WorkProvider workProvider, System.Boolean isIndustrial, System.Int32 level, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.WorkplaceData workplaceData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters);
    public static System.Int32 GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters);
    public static System.Int32 GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters);
    public static System.Int32 GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters);
    public static System.Int32 GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Game.Prefabs.EconomyParameterData& economyParameters);
    public static System.Int32 GetCompanyProfitPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters);
    public static System.Single GetCompanyProfitPerUnit(System.Boolean isIndustrial, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
    public static System.Int32 GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> vehicles, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layouts, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTrucks, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
    public static System.Int32 GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
    public static System.Int32 GetHouseholdIncome(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Collections.NativeArray<System.Int32> taxRates);
    public static System.Int32 GetHouseholdSpendableMoney(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_RenterBufs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Game.Buildings.PropertyRenter propertyRenter);
    public static System.Int32 GetHouseholdTotalWealth(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources);
    public static Game.City.IncomeSource GetIncomeSource(Game.City.PlayerResource resource);
    public static System.Single GetIndustrialPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
    public static System.Int64 GetLastTradeRequestTime(Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs);
    public static System.Single GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
    public static System.Single GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.EntityManager entityManager);
    public static System.Single GetMarketPrice(Game.Prefabs.ResourceData data);
    public static System.String GetName(Game.Economy.Resource r);
    public static Unity.Collections.FixedString32Bytes GetNameFixed(Game.Economy.Resource r);
    public static System.String GetNames(Game.Economy.Resource r);
    public static System.Boolean GetProcessComplexity(Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_IndustrialProcessDataChunks, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Game.Economy.Resource r, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.IndustrialProcessData> processType, Game.Prefabs.WorkplaceComplexity& complexity);
    public static Game.Economy.Resource GetResource(Game.Economy.ResourceInEditor resource);
    public static Game.Economy.Resource GetResource(System.Int32 index);
    public static Game.Economy.Resource GetResource(Game.Net.AvailableResource available);
    public static UnityEngine.Color GetResourceColor(Game.Economy.Resource r);
    public static System.Int32 GetResourceIndex(Game.Economy.Resource r);
    public static Game.Economy.Resource GetResources(Game.Economy.ResourceInEditor[] resources, Game.Economy.Resource defaultResources);
    public static System.Int32 GetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources);
    public static System.Single GetServicePrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
    public static System.Single GetServicePriceMultiplier(System.Single serviceAvailable, System.Int32 maxServiceAvailable);
    public static System.Int32 GetTotalStorageUsed(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources);
    public static Game.Companies.TradeCost GetTradeCost(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs);
    public static System.Int32 GetTransportCost(System.Single distance, Game.Economy.Resource resource, System.Int32 amount, System.Single weight);
    public static System.Single GetTransportCost(System.Single distance, System.Int32 amount, System.Single weight, Game.Companies.StorageTransferFlags flags);
    public static System.Single GetWeight(Unity.Entities.EntityManager entityManager, Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs);
    public static System.Single GetWeight(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas);
    public static System.Single GetWorkerWorkforce(System.Int32 happiness, System.Int32 level);
    public static System.Single GetWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
    public static System.Boolean IsCommercialResource(Game.Economy.Resource resource);
    public static System.Boolean IsExtractorResource(Game.Economy.Resource resource);
    public static System.Boolean IsIndustrialResource(Game.Prefabs.ResourceData resourceData, System.Boolean includeMaterial, System.Boolean includeOffice);
    public static System.Boolean IsMaterial(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas);
    public static System.Boolean IsOfficeResource(Game.Economy.Resource resource);
    public static System.Boolean IsProducedFrom(Game.Economy.Resource product, Game.Economy.Resource material);
    public static System.Void SetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, System.Int32 amount);
    public static System.Void SetTradeCost(Game.Economy.Resource resource, Game.Companies.TradeCost newcost, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs, System.Boolean keepLastTime, System.Single buyLerp, System.Single sellLerp);
}
```


## Fields

- `public static readonly System.Int32 kCompanyUpdatesPerDay`  

```csharp
public static readonly System.Int32 kCompanyUpdatesPerDay;
```

- `public static readonly System.Int32 ResourceCount`  

```csharp
public static readonly System.Int32 ResourceCount;
```


## Constructors

- `public EconomyUtils()`  

```csharp
public EconomyUtils();
```


## Methods

- `public static AddResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  

```csharp
public static void AddResources(DynamicBuffer<Resources> from, DynamicBuffer<Resources> to)
	{
		for (int i = 0; i < from.Length; i++)
		{
			AddResources(from[i].m_Resource, from[i].m_Amount, to);
		}
	}
```

- `public static AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> from, Unity.Entities.DynamicBuffer<Game.Economy.Resources> to) : System.Void`  

```csharp
public static void AddResources(DynamicBuffer<Resources> from, DynamicBuffer<Resources> to)
	{
		for (int i = 0; i < from.Length; i++)
		{
			AddResources(from[i].m_Resource, from[i].m_Amount, to);
		}
	}
```

- `public static BuildPseudoTradeCost(System.Single distance, Game.Prefabs.IndustrialProcessData process, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs) : Unity.Mathematics.float3`  

```csharp
public static float3 BuildPseudoTradeCost(float distance, IndustrialProcessData process, ref ComponentLookup<ResourceData> resourceDatas, ResourcePrefabs resourcePrefabs)
	{
		float3 @float = default(float3);
		if (process.m_Input1.m_Resource != Resource.NoResource)
		{
			@float.y = GetTransportCost(distance, process.m_Input1.m_Resource, 20000, resourceDatas[resourcePrefabs[process.m_Input1.m_Resource]].m_Weight);
		}
		if (process.m_Input2.m_Resource != Resource.NoResource)
		{
			@float.z = GetTransportCost(distance, process.m_Input2.m_Resource, 20000, resourceDatas[resourcePrefabs[process.m_Input2.m_Resource]].m_Weight);
		}
		@float.x = (float)GetTransportCost(distance, process.m_Output.m_Resource, 20000, resourceDatas[resourcePrefabs[process.m_Output.m_Resource]].m_Weight) - (@float.y * (float)process.m_Input1.m_Amount - @float.z * (float)process.m_Input2.m_Amount) / (float)process.m_Output.m_Amount;
		return @float / 20000f;
	}
```

- `public static CalculateNumberOfWorkplaces(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel) : Game.Companies.Workplaces`  

```csharp
public static Workplaces CalculateNumberOfWorkplaces(int totalWorkers, WorkplaceComplexity complexity, int buildingLevel)
	{
		Workplaces result = default(Workplaces);
		int num = 4 * (int)complexity + buildingLevel - 1;
		int num2 = totalWorkers;
		int num3 = 0;
		for (int i = 0; i < 5; i++)
		{
			int num4 = math.max(0, 8 - math.abs(num - 4 * i));
			if (i == 0)
			{
				num4 += math.max(0, 8 - math.abs(num + 4));
			}
			if (i == 4)
			{
				num4 += math.max(0, 8 - math.abs(num - 20));
			}
			int num5 = totalWorkers * num4 / 16;
			int num6 = totalWorkers * num4 % 16;
			if (num2 > num5 && num6 + num3 > 0)
			{
				num5++;
				num3 -= 16;
			}
			num3 += num6;
			num5 = math.min(num5, num2);
			num2 -= num5;
			result[i] = num5;
		}
		return result;
	}
```

- `public static CalculateTotalWage(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.EconomyParameterData& econParams) : System.Int32`  

```csharp
public static int CalculateTotalWage(int totalWorkers, WorkplaceComplexity complexity, int buildingLevel, EconomyParameterData econParams)
	{
		int num = 0;
		Workplaces workplaces = CalculateNumberOfWorkplaces(totalWorkers, complexity, buildingLevel);
		for (int i = 0; i < 5; i++)
		{
			num += workplaces[i] * econParams.GetWage(i);
		}
		return num;
	}
```

- `public static CalculateTotalWage(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel, Game.Prefabs.EconomyParameterData econParams) : System.Int32`  

```csharp
public static int CalculateTotalWage(int totalWorkers, WorkplaceComplexity complexity, int buildingLevel, EconomyParameterData econParams)
	{
		int num = 0;
		Workplaces workplaces = CalculateNumberOfWorkplaces(totalWorkers, complexity, buildingLevel);
		for (int i = 0; i < 5; i++)
		{
			num += workplaces[i] * econParams.GetWage(i);
		}
		return num;
	}
```

- `public static CountResources(Game.Economy.Resource resource) : System.Int32`  

```csharp
public static int CountResources(Resource resource)
	{
		int num = 0;
		ResourceIterator iterator = ResourceIterator.GetIterator();
		while (iterator.Next())
		{
			if ((resource & iterator.resource) != Resource.NoResource)
			{
				num++;
			}
		}
		return num;
	}
```

- `public static GetAllResources() : Game.Economy.Resource`  

```csharp
public static Resource GetAllResources()
	{
		return (Resource)2199023255551uL;
	}
```

- `public static GetAvailableResourceSupply(Game.Economy.Resource resource) : Game.Net.AvailableResource`  

```csharp
public static AvailableResource GetAvailableResourceSupply(Resource resource)
	{
		return resource switch
		{
			Resource.Grain => AvailableResource.GrainSupply, 
			Resource.Wood => AvailableResource.WoodSupply, 
			Resource.ConvenienceFood => AvailableResource.ConvenienceFoodSupply, 
			Resource.Paper => AvailableResource.PaperSupply, 
			Resource.Vehicles => AvailableResource.VehiclesSupply, 
			Resource.Oil => AvailableResource.OilSupply, 
			Resource.Petrochemicals => AvailableResource.PetrochemicalsSupply, 
			Resource.Ore => AvailableResource.OreSupply, 
			Resource.Metals => AvailableResource.MetalsSupply, 
			Resource.Electronics => AvailableResource.ElectronicsSupply, 
			Resource.Plastics => AvailableResource.PlasticsSupply, 
			Resource.Coal => AvailableResource.CoalSupply, 
			Resource.Stone => AvailableResource.StoneSupply, 
			Resource.Cotton => AvailableResource.CottonSupply, 
			Resource.Livestock => AvailableResource.LivestockSupply, 
			Resource.Vegetables => AvailableResource.VegetableSupply, 
			Resource.Steel => AvailableResource.SteelSupply, 
			Resource.Minerals => AvailableResource.MineralSupply, 
			Resource.Chemicals => AvailableResource.ChemicalSupply, 
			Resource.Timber => AvailableResource.TimberSupply, 
			Resource.Machinery => AvailableResource.MachinerySupply, 
			Resource.Beverages => AvailableResource.BeveragesSupply, 
			Resource.Textiles => AvailableResource.TextilesSupply, 
			Resource.Fish => AvailableResource.FishSupply, 
			_ => AvailableResource.Count, 
		};
	}
```

- `public static GetAverageWorkforce(System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel) : System.Single`  

```csharp
public static float GetAverageWorkforce(DynamicBuffer<Employee> employees)
	{
		float num = 0f;
		foreach (Employee item in employees)
		{
			num += GetWorkerWorkforce(50, item.m_Level);
		}
		return num;
	}
```

- `public static GetAverageWorkforce(Game.Companies.Workplaces workplaces) : System.Single`  

```csharp
public static float GetAverageWorkforce(DynamicBuffer<Employee> employees)
	{
		float num = 0f;
		foreach (Employee item in employees)
		{
			num += GetWorkerWorkforce(50, item.m_Level);
		}
		return num;
	}
```

- `public static GetAverageWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees) : System.Single`  

```csharp
public static float GetAverageWorkforce(DynamicBuffer<Employee> employees)
	{
		float num = 0f;
		foreach (Employee item in employees)
		{
			num += GetWorkerWorkforce(50, item.m_Level);
		}
		return num;
	}
```

- `public static GetCompanyMaxProfitPerDay(Game.Companies.WorkProvider workProvider, System.Boolean isIndustrial, System.Int32 level, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.WorkplaceData workplaceData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static int GetCompanyMaxProfitPerDay(WorkProvider workProvider, bool isIndustrial, int level, IndustrialProcessData processData, ResourcePrefabs resourcePrefabs, WorkplaceData workplaceData, ref ComponentLookup<ResourceData> resourceDatas, ref EconomyParameterData economyParameters)
	{
		int num = CalculateTotalWage(workProvider.m_MaxWorkers, workplaceData.m_Complexity, level, economyParameters);
		int companyProductionPerDay = GetCompanyProductionPerDay(1f, workProvider.m_MaxWorkers, level, isIndustrial, workplaceData, processData, resourcePrefabs, ref resourceDatas, ref economyParameters);
		return Mathf.RoundToInt(GetCompanyProfitPerUnit(isIndustrial, processData, resourcePrefabs, ref resourceDatas) * (float)companyProductionPerDay - (float)num);
	}
```

- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static int GetCompanyProductionPerDay(float buildingEfficiency, int workerAmount, int level, bool isIndustrial, WorkplaceData workplaceData, IndustrialProcessData processData, ResourceData resourceData, ref EconomyParameterData economyParameters)
	{
		float num = (IsExtractorResource(processData.m_Output.m_Resource) ? economyParameters.m_ExtractorProductionEfficiency : (isIndustrial ? economyParameters.m_IndustrialEfficiency : economyParameters.m_CommercialEfficiency));
		float num2 = buildingEfficiency * num * GetAverageWorkforce(workerAmount, workplaceData.m_Complexity, level) * (float)kCompanyUpdatesPerDay;
		float num3 = (isIndustrial ? resourceData.m_NeededWorkPerUnit.x : resourceData.m_NeededWorkPerUnit.y);
		return (int)math.ceil((float)processData.m_Output.m_Amount * (num2 / num3));
	}
```

- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static int GetCompanyProductionPerDay(float buildingEfficiency, int workerAmount, int level, bool isIndustrial, WorkplaceData workplaceData, IndustrialProcessData processData, ResourceData resourceData, ref EconomyParameterData economyParameters)
	{
		float num = (IsExtractorResource(processData.m_Output.m_Resource) ? economyParameters.m_ExtractorProductionEfficiency : (isIndustrial ? economyParameters.m_IndustrialEfficiency : economyParameters.m_CommercialEfficiency));
		float num2 = buildingEfficiency * num * GetAverageWorkforce(workerAmount, workplaceData.m_Complexity, level) * (float)kCompanyUpdatesPerDay;
		float num3 = (isIndustrial ? resourceData.m_NeededWorkPerUnit.x : resourceData.m_NeededWorkPerUnit.y);
		return (int)math.ceil((float)processData.m_Output.m_Amount * (num2 / num3));
	}
```

- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static int GetCompanyProductionPerDay(float buildingEfficiency, int workerAmount, int level, bool isIndustrial, WorkplaceData workplaceData, IndustrialProcessData processData, ResourceData resourceData, ref EconomyParameterData economyParameters)
	{
		float num = (IsExtractorResource(processData.m_Output.m_Resource) ? economyParameters.m_ExtractorProductionEfficiency : (isIndustrial ? economyParameters.m_IndustrialEfficiency : economyParameters.m_CommercialEfficiency));
		float num2 = buildingEfficiency * num * GetAverageWorkforce(workerAmount, workplaceData.m_Complexity, level) * (float)kCompanyUpdatesPerDay;
		float num3 = (isIndustrial ? resourceData.m_NeededWorkPerUnit.x : resourceData.m_NeededWorkPerUnit.y);
		return (int)math.ceil((float)processData.m_Output.m_Amount * (num2 / num3));
	}
```

- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static int GetCompanyProductionPerDay(float buildingEfficiency, int workerAmount, int level, bool isIndustrial, WorkplaceData workplaceData, IndustrialProcessData processData, ResourceData resourceData, ref EconomyParameterData economyParameters)
	{
		float num = (IsExtractorResource(processData.m_Output.m_Resource) ? economyParameters.m_ExtractorProductionEfficiency : (isIndustrial ? economyParameters.m_IndustrialEfficiency : economyParameters.m_CommercialEfficiency));
		float num2 = buildingEfficiency * num * GetAverageWorkforce(workerAmount, workplaceData.m_Complexity, level) * (float)kCompanyUpdatesPerDay;
		float num3 = (isIndustrial ? resourceData.m_NeededWorkPerUnit.x : resourceData.m_NeededWorkPerUnit.y);
		return (int)math.ceil((float)processData.m_Output.m_Amount * (num2 / num3));
	}
```

- `public static GetCompanyProfitPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static int GetCompanyProfitPerDay(float buildingEfficiency, bool isIndustrial, DynamicBuffer<Employee> employees, IndustrialProcessData processData, ResourcePrefabs resourcePrefabs, ref ComponentLookup<ResourceData> resourceDatas, ref ComponentLookup<Citizen> citizens, ref EconomyParameterData economyParameters)
	{
		int num = CalculateTotalWage(employees, ref economyParameters);
		int companyProductionPerDay = GetCompanyProductionPerDay(buildingEfficiency, isIndustrial, employees, processData, resourcePrefabs, ref resourceDatas, ref citizens, ref economyParameters);
		return Mathf.RoundToInt(GetCompanyProfitPerUnit(isIndustrial, processData, resourcePrefabs, ref resourceDatas) * (float)companyProductionPerDay - (float)num);
	}
```

- `public static GetCompanyProfitPerUnit(System.Boolean isIndustrial, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static float GetCompanyProfitPerUnit(bool isIndustrial, IndustrialProcessData processData, ResourcePrefabs resourcePrefabs, ref ComponentLookup<ResourceData> resourceDatas)
	{
		return ((isIndustrial ? GetIndustrialPrice(processData.m_Output.m_Resource, resourcePrefabs, ref resourceDatas) : GetMarketPrice(processData.m_Output.m_Resource, resourcePrefabs, ref resourceDatas)) * (float)processData.m_Output.m_Amount - (float)processData.m_Input1.m_Amount * GetIndustrialPrice(processData.m_Input1.m_Resource, resourcePrefabs, ref resourceDatas) - (float)processData.m_Input2.m_Amount * GetIndustrialPrice(processData.m_Input2.m_Resource, resourcePrefabs, ref resourceDatas)) / (float)processData.m_Output.m_Amount;
	}
```

- `public static GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> vehicles, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layouts, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTrucks, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Int32`  

```csharp
public static int GetCompanyTotalWorth(DynamicBuffer<Resources> resources, ResourcePrefabs resourcePrefabs, ref ComponentLookup<ResourceData> resourceDatas)
	{
		int num = 0;
		for (int i = 0; i < resources.Length; i++)
		{
			num += Mathf.RoundToInt((float)resources[i].m_Amount * GetIndustrialPrice(resources[i].m_Resource, resourcePrefabs, ref resourceDatas));
		}
		return num;
	}
```

- `public static GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Int32`  

```csharp
public static int GetCompanyTotalWorth(DynamicBuffer<Resources> resources, ResourcePrefabs resourcePrefabs, ref ComponentLookup<ResourceData> resourceDatas)
	{
		int num = 0;
		for (int i = 0; i < resources.Length; i++)
		{
			num += Mathf.RoundToInt((float)resources[i].m_Amount * GetIndustrialPrice(resources[i].m_Resource, resourcePrefabs, ref resourceDatas));
		}
		return num;
	}
```

- `public static GetHouseholdIncome(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static int GetHouseholdIncome(DynamicBuffer<HouseholdCitizen> citizens, ref ComponentLookup<Worker> workers, ref ComponentLookup<Citizen> citizenDatas, ref ComponentLookup<HealthProblem> healthProblems, ref EconomyParameterData economyParameters, NativeArray<int> taxRates)
	{
		int num = 0;
		for (int i = 0; i < citizens.Length; i++)
		{
			Entity citizen = citizens[i].m_Citizen;
			if (CitizenUtils.IsDead(citizen, ref healthProblems))
			{
				continue;
			}
			CitizenAge age = citizenDatas[citizen].GetAge();
			if (workers.HasComponent(citizen))
			{
				int level = workers[citizen].m_Level;
				int wage = economyParameters.GetWage(level);
				num += wage;
				int num2 = wage - economyParameters.m_ResidentialMinimumEarnings;
				if (num2 > 0)
				{
					num -= Mathf.RoundToInt((float)num2 * ((float)TaxSystem.GetResidentialTaxRate(level, taxRates) / 100f));
				}
				continue;
			}
			switch (age)
			{
			case CitizenAge.Child:
			case CitizenAge.Teen:
				num += economyParameters.m_FamilyAllowance;
				continue;
			case CitizenAge.Elderly:
				num += economyParameters.m_Pension;
				continue;
			}
			if ((float)citizenDatas[citizen].m_UnemploymentCounter < economyParameters.m_UnemploymentAllowanceMaxDays * (float)PayWageSystem.kUpdatesPerDay)
			{
				num += economyParameters.m_UnemploymentBenefit;
			}
		}
		return Mathf.RoundToInt(num);
	}
```

- `public static GetHouseholdSpendableMoney(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_RenterBufs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Game.Buildings.PropertyRenter propertyRenter) : System.Int32`  

```csharp
public static int GetHouseholdSpendableMoney(Household householdData, DynamicBuffer<Resources> resources, ref BufferLookup<Renter> m_RenterBufs, ref ComponentLookup<ConsumptionData> consumptionDatas, ref ComponentLookup<PrefabRef> prefabRefs, PropertyRenter propertyRenter)
	{
		int num = GetResources(Resource.Money, resources);
		if (propertyRenter.m_Property != Entity.Null && m_RenterBufs.HasBuffer(propertyRenter.m_Property))
		{
			int length = m_RenterBufs[propertyRenter.m_Property].Length;
			num -= propertyRenter.m_Rent;
			Entity prefab = prefabRefs[propertyRenter.m_Property].m_Prefab;
			if (length == 0)
			{
				UnityEngine.Debug.LogWarning($"Property:{propertyRenter.m_Property.Index} has 0 renter");
			}
			int num2 = consumptionDatas[prefab].m_Upkeep / (length + 1);
			num -= num2;
		}
		return num;
	}
```

- `public static GetHouseholdTotalWealth(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  

```csharp
public static int GetHouseholdTotalWealth(Household householdData, DynamicBuffer<Resources> resources)
	{
		int resources2 = GetResources(Resource.Money, resources);
		return (int)math.min(2147483647L, (long)householdData.m_Resources + (long)resources2);
	}
```

- `public static GetIncomeSource(Game.City.PlayerResource resource) : Game.City.IncomeSource`  

```csharp
public static IncomeSource GetIncomeSource(PlayerResource resource)
	{
		switch (resource)
		{
		case PlayerResource.Electricity:
			return IncomeSource.FeeElectricity;
		case PlayerResource.Healthcare:
			return IncomeSource.FeeHealthcare;
		case PlayerResource.BasicEducation:
		case PlayerResource.SecondaryEducation:
		case PlayerResource.HigherEducation:
			return IncomeSource.FeeEducation;
		case PlayerResource.Water:
		case PlayerResource.Sewage:
			return IncomeSource.FeeWater;
		case PlayerResource.PublicTransport:
			return IncomeSource.FeePublicTransport;
		case PlayerResource.Parking:
			return IncomeSource.FeeParking;
		case PlayerResource.Garbage:
			return IncomeSource.FeeGarbage;
		default:
			return IncomeSource.Count;
		}
	}
```

- `public static GetIndustrialPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static float GetIndustrialPrice(Resource r, ResourcePrefabs prefabs, ref ComponentLookup<ResourceData> resourceDatas)
	{
		Entity entity = prefabs[r];
		if (resourceDatas.HasComponent(entity))
		{
			return resourceDatas[entity].m_Price.x;
		}
		return 0f;
	}
```

- `public static GetLastTradeRequestTime(Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs) : System.Int64`  

```csharp
public static long GetLastTradeRequestTime(DynamicBuffer<TradeCost> costs)
	{
		long num = 0L;
		for (int i = 0; i < costs.Length; i++)
		{
			TradeCost tradeCost = costs[i];
			if (tradeCost.m_LastTransferRequestTime > num)
			{
				num = tradeCost.m_LastTransferRequestTime;
			}
		}
		return num;
	}
```

- `public static GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static float GetMarketPrice(ResourceData data)
	{
		return data.m_Price.x + data.m_Price.y;
	}
```

- `public static GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.EntityManager entityManager) : System.Single`  

```csharp
public static float GetMarketPrice(ResourceData data)
	{
		return data.m_Price.x + data.m_Price.y;
	}
```

- `public static GetMarketPrice(Game.Prefabs.ResourceData data) : System.Single`  

```csharp
public static float GetMarketPrice(ResourceData data)
	{
		return data.m_Price.x + data.m_Price.y;
	}
```

- `public static GetName(Game.Economy.Resource r) : System.String`  

```csharp
public static string GetName(Resource r)
	{
		switch (r)
		{
		case Resource.NoResource:
		case Resource.Money:
		case Resource.Grain:
		case (Resource)3uL:
		case Resource.ConvenienceFood:
		case (Resource)5uL:
		case (Resource)6uL:
		case (Resource)7uL:
		case Resource.Food:
		case (Resource)9uL:
		case (Resource)10uL:
		case (Resource)11uL:
		case (Resource)12uL:
		case (Resource)13uL:
		case (Resource)14uL:
		case (Resource)15uL:
		case Resource.Vegetables:
			if (r <= Resource.Food)
			{
				switch (r)
				{
				case Resource.NoResource:
					return "none";
				case Resource.Grain:
					return "grain";
				case Resource.ConvenienceFood:
					return "conv.food";
				case Resource.Food:
					return "food";
				case Resource.Money:
					return "money";
				case (Resource)3uL:
				case (Resource)5uL:
				case (Resource)6uL:
				case (Resource)7uL:
					goto end_IL_0007;
				}
			}
			if (r != Resource.Vegetables)
			{
				break;
			}
			return "vegetables";
		case Resource.Furniture:
			return "furniture";
		case Resource.Meals:
			return "meals";
		case Resource.Paper:
			return "paper";
		case Resource.Timber:
			return "timber";
		case Resource.Vehicles:
			return "vehicles";
		case Resource.Wood:
			return "wood";
		case Resource.Lodging:
			return "lodging";
		case Resource.UnsortedMail:
			return "unsorted mail";
		case Resource.LocalMail:
			return "local mail";
		case Resource.OutgoingMail:
			return "outgoing mail";
		case Resource.Oil:
			return "oil";
		case Resource.Petrochemicals:
			return "petrochemicals";
		case Resource.Ore:
			return "ore";
		case Resource.Plastics:
			return "plastics";
		case Resource.Metals:
			return "metals";
		case Resource.Electronics:
			return "electronics";
		case Resource.Software:
			return "software";
		case Resource.Coal:
			return "coal";
		case Resource.Stone:
			return "stone";
		case Resource.Livestock:
			return "livestock";
		case Resource.Cotton:
			return "cotton";
		case Resource.Steel:
			return "steel";
		case Resource.Minerals:
			return "minerals";
		case Resource.Concrete:
			return "concrete";
		case Resource.Machinery:
			return "machinery";
		case Resource.Chemicals:
			return "chemicals";
		case Resource.Pharmaceuticals:
			return "pharmaceuticals";
		case Resource.Beverages:
			return "beverages";
		case Resource.Textiles:
			return "textiles";
		case Resource.Telecom:
			return "telecom";
		case Resource.Financial:
			return "financial";
		case Resource.Media:
			return "media";
		case Resource.Entertainment:
			return "entertainment";
		case Resource.Recreation:
			return "recreation";
		case Resource.Garbage:
			return "garbage";
		case Resource.Fish:
			{
				return "fish";
			}
			end_IL_0007:
			break;
		}
		return "none";
	}
```

- `public static GetNameFixed(Game.Economy.Resource r) : Unity.Collections.FixedString32Bytes`  

```csharp
public static FixedString32Bytes GetNameFixed(Resource r)
	{
		switch (r)
		{
		case Resource.NoResource:
		case Resource.Money:
		case Resource.Grain:
		case (Resource)3uL:
		case Resource.ConvenienceFood:
		case (Resource)5uL:
		case (Resource)6uL:
		case (Resource)7uL:
		case Resource.Food:
		case (Resource)9uL:
		case (Resource)10uL:
		case (Resource)11uL:
		case (Resource)12uL:
		case (Resource)13uL:
		case (Resource)14uL:
		case (Resource)15uL:
		case Resource.Vegetables:
			if (r <= Resource.Food)
			{
				switch (r)
				{
				case Resource.NoResource:
					return "none";
				case Resource.Grain:
					return "grain";
				case Resource.ConvenienceFood:
					return "conv.food";
				case Resource.Food:
					return "food";
				case Resource.Money:
					return "money";
				case (Resource)3uL:
				case (Resource)5uL:
				case (Resource)6uL:
				case (Resource)7uL:
					goto end_IL_0007;
				}
			}
			if (r != Resource.Vegetables)
			{
				break;
			}
			return "vegetables";
		case Resource.Furniture:
			return "furniture";
		case Resource.Meals:
			return "meals";
		case Resource.Paper:
			return "paper";
		case Resource.Timber:
			return "timber";
		case Resource.Vehicles:
			return "vehicles";
		case Resource.Wood:
			return "wood";
		case Resource.Lodging:
			return "lodging";
		case Resource.UnsortedMail:
			return "unsorted mail";
		case Resource.LocalMail:
			return "local mail";
		case Resource.OutgoingMail:
			return "outgoing mail";
		case Resource.Oil:
			return "oil";
		case Resource.Petrochemicals:
			return "petrochemicals";
		case Resource.Ore:
			return "ore";
		case Resource.Plastics:
			return "plastics";
		case Resource.Metals:
			return "metals";
		case Resource.Electronics:
			return "electronics";
		case Resource.Software:
			return "software";
		case Resource.Coal:
			return "coal";
		case Resource.Stone:
			return "stone";
		case Resource.Livestock:
			return "livestock";
		case Resource.Cotton:
			return "cotton";
		case Resource.Steel:
			return "steel";
		case Resource.Minerals:
			return "minerals";
		case Resource.Concrete:
			return "concrete";
		case Resource.Machinery:
			return "machinery";
		case Resource.Chemicals:
			return "chemicals";
		case Resource.Pharmaceuticals:
			return "pharmaceuticals";
		case Resource.Beverages:
			return "beverages";
		case Resource.Textiles:
			return "textiles";
		case Resource.Telecom:
			return "telecom";
		case Resource.Financial:
			return "financial";
		case Resource.Media:
			return "media";
		case Resource.Entertainment:
			return "entertainment";
		case Resource.Recreation:
			return "recreation";
		case Resource.Garbage:
			return "garbage";
		case Resource.Fish:
			{
				return "fish";
			}
			end_IL_0007:
			break;
		}
		return "none";
	}
```

- `public static GetNames(Game.Economy.Resource r) : System.String`  

```csharp
public static string GetNames(Resource r)
	{
		string text = "";
		for (int i = 0; i < ResourceCount; i++)
		{
			if ((r & GetResource(i)) != Resource.NoResource)
			{
				text = text + GetName(GetResource(i)) + "|";
			}
		}
		return text;
	}
```

- `public static GetProcessComplexity(Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_IndustrialProcessDataChunks, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Game.Economy.Resource r, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.IndustrialProcessData> processType, Game.Prefabs.WorkplaceComplexity& complexity) : System.Boolean`  

```csharp
public static bool GetProcessComplexity(NativeList<ArchetypeChunk> m_IndustrialProcessDataChunks, ref ComponentLookup<WorkplaceData> workplaceDatas, Resource r, EntityTypeHandle entityType, ComponentTypeHandle<IndustrialProcessData> processType, out WorkplaceComplexity complexity)
	{
		for (int i = 0; i < m_IndustrialProcessDataChunks.Length; i++)
		{
			ArchetypeChunk archetypeChunk = m_IndustrialProcessDataChunks[i];
			NativeArray<Entity> nativeArray = archetypeChunk.GetNativeArray(entityType);
			NativeArray<IndustrialProcessData> nativeArray2 = archetypeChunk.GetNativeArray(ref processType);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				if (nativeArray2[j].m_Output.m_Resource == r)
				{
					Entity entity = nativeArray[j];
					if (workplaceDatas.HasComponent(entity))
					{
						complexity = workplaceDatas[entity].m_Complexity;
						return true;
					}
				}
			}
		}
		complexity = WorkplaceComplexity.Simple;
		return false;
	}
```

- `public static GetResource(Game.Economy.ResourceInEditor resource) : Game.Economy.Resource`  

```csharp
public static Resource GetResource(AvailableResource available)
	{
		return available switch
		{
			AvailableResource.GrainSupply => Resource.Grain, 
			AvailableResource.TextilesSupply => Resource.Textiles, 
			AvailableResource.VegetableSupply => Resource.Vegetables, 
			AvailableResource.ConvenienceFoodSupply => Resource.ConvenienceFood, 
			AvailableResource.PaperSupply => Resource.Paper, 
			AvailableResource.VehiclesSupply => Resource.Vehicles, 
			AvailableResource.WoodSupply => Resource.Wood, 
			AvailableResource.MetalsSupply => Resource.Metals, 
			AvailableResource.OilSupply => Resource.Oil, 
			AvailableResource.OreSupply => Resource.Ore, 
			AvailableResource.PetrochemicalsSupply => Resource.Petrochemicals, 
			AvailableResource.ElectronicsSupply => Resource.Electronics, 
			AvailableResource.PlasticsSupply => Resource.Plastics, 
			AvailableResource.CoalSupply => Resource.Coal, 
			AvailableResource.StoneSupply => Resource.Stone, 
			AvailableResource.LivestockSupply => Resource.Livestock, 
			AvailableResource.CottonSupply => Resource.Cotton, 
			AvailableResource.SteelSupply => Resource.Steel, 
			AvailableResource.MineralSupply => Resource.Minerals, 
			AvailableResource.ChemicalSupply => Resource.Chemicals, 
			AvailableResource.BeveragesSupply => Resource.Beverages, 
			AvailableResource.TimberSupply => Resource.Timber, 
			AvailableResource.MachinerySupply => Resource.Machinery, 
			AvailableResource.FishSupply => Resource.Fish, 
			_ => Resource.NoResource, 
		};
	}
```

- `public static GetResource(System.Int32 index) : Game.Economy.Resource`  

```csharp
public static Resource GetResource(AvailableResource available)
	{
		return available switch
		{
			AvailableResource.GrainSupply => Resource.Grain, 
			AvailableResource.TextilesSupply => Resource.Textiles, 
			AvailableResource.VegetableSupply => Resource.Vegetables, 
			AvailableResource.ConvenienceFoodSupply => Resource.ConvenienceFood, 
			AvailableResource.PaperSupply => Resource.Paper, 
			AvailableResource.VehiclesSupply => Resource.Vehicles, 
			AvailableResource.WoodSupply => Resource.Wood, 
			AvailableResource.MetalsSupply => Resource.Metals, 
			AvailableResource.OilSupply => Resource.Oil, 
			AvailableResource.OreSupply => Resource.Ore, 
			AvailableResource.PetrochemicalsSupply => Resource.Petrochemicals, 
			AvailableResource.ElectronicsSupply => Resource.Electronics, 
			AvailableResource.PlasticsSupply => Resource.Plastics, 
			AvailableResource.CoalSupply => Resource.Coal, 
			AvailableResource.StoneSupply => Resource.Stone, 
			AvailableResource.LivestockSupply => Resource.Livestock, 
			AvailableResource.CottonSupply => Resource.Cotton, 
			AvailableResource.SteelSupply => Resource.Steel, 
			AvailableResource.MineralSupply => Resource.Minerals, 
			AvailableResource.ChemicalSupply => Resource.Chemicals, 
			AvailableResource.BeveragesSupply => Resource.Beverages, 
			AvailableResource.TimberSupply => Resource.Timber, 
			AvailableResource.MachinerySupply => Resource.Machinery, 
			AvailableResource.FishSupply => Resource.Fish, 
			_ => Resource.NoResource, 
		};
	}
```

- `public static GetResource(Game.Net.AvailableResource available) : Game.Economy.Resource`  

```csharp
public static Resource GetResource(AvailableResource available)
	{
		return available switch
		{
			AvailableResource.GrainSupply => Resource.Grain, 
			AvailableResource.TextilesSupply => Resource.Textiles, 
			AvailableResource.VegetableSupply => Resource.Vegetables, 
			AvailableResource.ConvenienceFoodSupply => Resource.ConvenienceFood, 
			AvailableResource.PaperSupply => Resource.Paper, 
			AvailableResource.VehiclesSupply => Resource.Vehicles, 
			AvailableResource.WoodSupply => Resource.Wood, 
			AvailableResource.MetalsSupply => Resource.Metals, 
			AvailableResource.OilSupply => Resource.Oil, 
			AvailableResource.OreSupply => Resource.Ore, 
			AvailableResource.PetrochemicalsSupply => Resource.Petrochemicals, 
			AvailableResource.ElectronicsSupply => Resource.Electronics, 
			AvailableResource.PlasticsSupply => Resource.Plastics, 
			AvailableResource.CoalSupply => Resource.Coal, 
			AvailableResource.StoneSupply => Resource.Stone, 
			AvailableResource.LivestockSupply => Resource.Livestock, 
			AvailableResource.CottonSupply => Resource.Cotton, 
			AvailableResource.SteelSupply => Resource.Steel, 
			AvailableResource.MineralSupply => Resource.Minerals, 
			AvailableResource.ChemicalSupply => Resource.Chemicals, 
			AvailableResource.BeveragesSupply => Resource.Beverages, 
			AvailableResource.TimberSupply => Resource.Timber, 
			AvailableResource.MachinerySupply => Resource.Machinery, 
			AvailableResource.FishSupply => Resource.Fish, 
			_ => Resource.NoResource, 
		};
	}
```

- `public static GetResourceColor(Game.Economy.Resource r) : UnityEngine.Color`  

```csharp
public static Color GetResourceColor(Resource r)
	{
		switch (r)
		{
		case Resource.NoResource:
		case Resource.Money:
		case Resource.Grain:
		case (Resource)3uL:
		case Resource.ConvenienceFood:
		case (Resource)5uL:
		case (Resource)6uL:
		case (Resource)7uL:
		case Resource.Food:
		case (Resource)9uL:
		case (Resource)10uL:
		case (Resource)11uL:
		case (Resource)12uL:
		case (Resource)13uL:
		case (Resource)14uL:
		case (Resource)15uL:
		case Resource.Vegetables:
			if (r <= Resource.Food)
			{
				switch (r)
				{
				case Resource.NoResource:
					return Color.white;
				case Resource.Grain:
					return new Color
					{
						r = 0.59607846f,
						g = 48f / 85f,
						b = 0.427451f,
						a = 1f
					};
				case Resource.ConvenienceFood:
					return new Color
					{
						r = 0.7607843f,
						g = 0.5480962f,
						b = 0.35294122f,
						a = 1f
					};
				case Resource.Food:
					return new Color
					{
						r = 0.59607846f,
						g = 0.1607843f,
						b = 0.26029193f,
						a = 1f
					};
				case Resource.Money:
					return new Color
					{
						r = 26f / 85f,
						g = 0.46274513f,
						b = 0.3372549f,
						a = 1f
					};
				case (Resource)3uL:
				case (Resource)5uL:
				case (Resource)6uL:
				case (Resource)7uL:
					goto end_IL_0007;
				}
			}
			if (r != Resource.Vegetables)
			{
				break;
			}
			return new Color
			{
				r = 0.55274945f,
				g = 87f / 106f,
				b = 0.37682444f,
				a = 1f
			};
		case Resource.Furniture:
			return new Color
			{
				r = 0.45098042f,
				g = 0.35686275f,
				b = 0.20000002f,
				a = 1f
			};
		case Resource.Meals:
			return new Color
			{
				r = 16f / 51f,
				g = 0.654902f,
				b = 29f / 51f,
				a = 1f
			};
		case Resource.Paper:
			return new Color
			{
				r = 0.8000001f,
				g = 0.7960785f,
				b = 0.6313726f,
				a = 1f
			};
		case Resource.Timber:
			return new Color
			{
				r = 0.4039216f,
				g = 0.28627452f,
				b = 13f / 85f,
				a = 1f
			};
		case Resource.Vehicles:
			return new Color
			{
				r = 16f / 51f,
				g = 0.38823533f,
				b = 0.47058827f,
				a = 1f
			};
		case Resource.Wood:
			return new Color
			{
				r = 0.4039216f,
				g = 0.3529412f,
				b = 0.29803923f,
				a = 1f
			};
		case Resource.Lodging:
			return new Color
			{
				r = 0.32156864f,
				g = 0.3803922f,
				b = 0.5921569f,
				a = 1f
			};
		case Resource.UnsortedMail:
			return new Color
			{
				r = 1f,
				g = 0.9921569f,
				b = 43f / 85f,
				a = 1f
			};
		case Resource.LocalMail:
			return new Color
			{
				r = 37f / 51f,
				g = 61f / 85f,
				b = 0.36078432f,
				a = 1f
			};
		case Resource.OutgoingMail:
			return new Color
			{
				r = 0.5372549f,
				g = 8f / 15f,
				b = 24f / 85f,
				a = 1f
			};
		case Resource.Oil:
			return new Color
			{
				r = 0.16862746f,
				g = 2f / 15f,
				b = 4f / 51f,
				a = 1f
			};
		case Resource.Petrochemicals:
			return new Color
			{
				r = 0.19032574f,
				g = 0.21465941f,
				b = 0.4433962f,
				a = 1f
			};
		case Resource.Ore:
			return new Color
			{
				r = 0.26143643f,
				g = 0.43639776f,
				b = 0.4433962f,
				a = 1f
			};
		case Resource.Plastics:
			return new Color
			{
				r = 0.29803923f,
				g = 0.4901961f,
				b = 0.86666673f,
				a = 1f
			};
		case Resource.Metals:
			return new Color
			{
				r = 0.48627454f,
				g = 0.48627454f,
				b = 0.48627454f,
				a = 1f
			};
		case Resource.Electronics:
			return new Color
			{
				r = 63f / 85f,
				g = 1f,
				b = 0.47450984f,
				a = 1f
			};
		case Resource.Software:
			return new Color
			{
				r = 0.7843138f,
				g = 0.6745098f,
				b = 0.7725491f,
				a = 1f
			};
		case Resource.Coal:
			return new Color
			{
				r = 0.1137255f,
				g = 0.1137255f,
				b = 0.14901961f,
				a = 1f
			};
		case Resource.Stone:
			return new Color
			{
				r = 0.227451f,
				g = 0.2509804f,
				b = 0.3019608f,
				a = 1f
			};
		case Resource.Livestock:
			return new Color
			{
				r = 0.7725491f,
				g = 0.7725491f,
				b = 0.7725491f,
				a = 1f
			};
		case Resource.Cotton:
			return new Color
			{
				r = 0.9568628f,
				g = 0.9568628f,
				b = 0.9568628f,
				a = 1f
			};
		case Resource.Steel:
			return new Color
			{
				r = 28f / 51f,
				g = 0.5921569f,
				b = 0.6039216f,
				a = 1f
			};
		case Resource.Minerals:
			return new Color
			{
				r = 46f / 85f,
				g = 0.4431373f,
				b = 0.6313726f,
				a = 1f
			};
		case Resource.Concrete:
			return new Color
			{
				r = 0.4039216f,
				g = 0.42352945f,
				b = 44f / 85f,
				a = 1f
			};
		case Resource.Machinery:
			return new Color
			{
				r = 27f / 85f,
				g = 0.36078432f,
				b = 0.9490197f,
				a = 1f
			};
		case Resource.Chemicals:
			return new Color
			{
				r = 0.39373434f,
				g = 0.7924528f,
				b = 0.49253064f,
				a = 1f
			};
		case Resource.Pharmaceuticals:
			return new Color
			{
				r = 0.78823537f,
				g = 47f / 85f,
				b = 0.6039216f,
				a = 1f
			};
		case Resource.Beverages:
			return new Color
			{
				r = 0.7843138f,
				g = 0.8000001f,
				b = 28f / 51f,
				a = 1f
			};
		case Resource.Textiles:
			return new Color
			{
				r = 0.9803922f,
				g = 28f / 51f,
				b = 0.9490197f,
				a = 1f
			};
		case Resource.Telecom:
			return new Color
			{
				r = 0.49803925f,
				g = 0.7960785f,
				b = 0.7058824f,
				a = 1f
			};
		case Resource.Financial:
			return new Color
			{
				r = 0.21264978f,
				g = 0.5283019f,
				b = 0.21951182f,
				a = 1f
			};
		case Resource.Media:
			return new Color
			{
				r = 0.2509804f,
				g = 0.80392164f,
				b = 0.83921576f,
				a = 1f
			};
		case Resource.Entertainment:
			return new Color
			{
				r = 0.91372555f,
				g = 0.3254902f,
				b = 0.3254902f,
				a = 1f
			};
		case Resource.Recreation:
			return new Color
			{
				r = 0.83921576f,
				g = 0.1764706f,
				b = 0.44705886f,
				a = 1f
			};
		case Resource.Garbage:
			return new Color
			{
				r = 0.3019608f,
				g = 18f / 85f,
				b = 18f / 85f,
				a = 1f
			};
		case Resource.Fish:
			{
				return new Color
				{
					r = 0.9725491f,
					g = 0.7725491f,
					b = 0.7725491f,
					a = 1f
				};
			}
			end_IL_0007:
			break;
		}
		return Color.black;
	}
```

- `public static GetResourceIndex(Game.Economy.Resource r) : System.Int32`  

```csharp
public static int GetResourceIndex(Resource r)
	{
		switch (r)
		{
		case Resource.NoResource:
		case Resource.Money:
		case Resource.Grain:
		case (Resource)3uL:
		case Resource.ConvenienceFood:
		case (Resource)5uL:
		case (Resource)6uL:
		case (Resource)7uL:
		case Resource.Food:
		{
			Resource num = r - 1;
			if (num <= (Resource)3uL)
			{
				switch (num)
				{
				case Resource.NoResource:
					return 0;
				case Resource.Money:
					return 1;
				case (Resource)3uL:
					return 2;
				case Resource.Grain:
					goto end_IL_0007;
				}
			}
			if (r != Resource.Food)
			{
				break;
			}
			return 3;
		}
		case Resource.Vegetables:
			return 4;
		case Resource.Meals:
			return 5;
		case Resource.Wood:
			return 6;
		case Resource.Timber:
			return 7;
		case Resource.Paper:
			return 8;
		case Resource.Furniture:
			return 9;
		case Resource.Vehicles:
			return 10;
		case Resource.Lodging:
			return 11;
		case Resource.UnsortedMail:
			return 12;
		case Resource.LocalMail:
			return 13;
		case Resource.OutgoingMail:
			return 14;
		case Resource.Oil:
			return 15;
		case Resource.Petrochemicals:
			return 16;
		case Resource.Ore:
			return 17;
		case Resource.Plastics:
			return 18;
		case Resource.Metals:
			return 19;
		case Resource.Electronics:
			return 20;
		case Resource.Software:
			return 21;
		case Resource.Coal:
			return 22;
		case Resource.Stone:
			return 23;
		case Resource.Livestock:
			return 24;
		case Resource.Cotton:
			return 25;
		case Resource.Steel:
			return 26;
		case Resource.Minerals:
			return 27;
		case Resource.Concrete:
			return 28;
		case Resource.Machinery:
			return 29;
		case Resource.Chemicals:
			return 30;
		case Resource.Pharmaceuticals:
			return 31;
		case Resource.Beverages:
			return 32;
		case Resource.Textiles:
			return 33;
		case Resource.Telecom:
			return 34;
		case Resource.Financial:
			return 35;
		case Resource.Media:
			return 36;
		case Resource.Entertainment:
			return 37;
		case Resource.Recreation:
			return 38;
		case Resource.Garbage:
			return 39;
		case Resource.Fish:
			return 40;
		case Resource.Last:
			{
				return 41;
			}
			end_IL_0007:
			break;
		}
		return -1;
	}
```

- `public static GetResources(Game.Economy.ResourceInEditor[] resources, Game.Economy.Resource defaultResources = NoResource) : Game.Economy.Resource`  

```csharp
public static int GetResources(Resource resource, DynamicBuffer<Resources> resources)
	{
		for (int i = 0; i < resources.Length; i++)
		{
			Resources resources2 = resources[i];
			if (resources2.m_Resource == resource)
			{
				return resources2.m_Amount;
			}
		}
		return 0;
	}
```

- `public static GetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  

```csharp
public static int GetResources(Resource resource, DynamicBuffer<Resources> resources)
	{
		for (int i = 0; i < resources.Length; i++)
		{
			Resources resources2 = resources[i];
			if (resources2.m_Resource == resource)
			{
				return resources2.m_Amount;
			}
		}
		return 0;
	}
```

- `public static GetServicePrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static float GetServicePrice(Resource r, ResourcePrefabs prefabs, ref ComponentLookup<ResourceData> resourceDatas)
	{
		Entity entity = prefabs[r];
		if (resourceDatas.HasComponent(entity))
		{
			return resourceDatas[entity].m_Price.y;
		}
		return 0f;
	}
```

- `public static GetServicePriceMultiplier(System.Single serviceAvailable, System.Int32 maxServiceAvailable) : System.Single`  

```csharp
public static float GetServicePriceMultiplier(float serviceAvailable, int maxServiceAvailable)
	{
		return math.lerp(0.7f, 1.3f, math.saturate(1f - serviceAvailable / (float)maxServiceAvailable));
	}
```

- `public static GetTotalStorageUsed(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  

```csharp
public static int GetTotalStorageUsed(DynamicBuffer<Resources> resources)
	{
		int num = 0;
		for (int i = 0; i < resources.Length; i++)
		{
			Resources resources2 = resources[i];
			if (resources2.m_Resource != Resource.Money)
			{
				num += resources2.m_Amount;
			}
		}
		return num;
	}
```

- `public static GetTradeCost(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs) : Game.Companies.TradeCost`  

```csharp
public static TradeCost GetTradeCost(Resource resource, DynamicBuffer<TradeCost> costs)
	{
		for (int i = 0; i < costs.Length; i++)
		{
			TradeCost result = costs[i];
			if (result.m_Resource == resource)
			{
				return result;
			}
		}
		return new TradeCost
		{
			m_Resource = resource
		};
	}
```

- `public static GetTransportCost(System.Single distance, Game.Economy.Resource resource, System.Int32 amount, System.Single weight) : System.Int32`  

```csharp
public static float GetTransportCost(float distance, int amount, float weight, StorageTransferFlags flags)
	{
		if ((flags & StorageTransferFlags.Car) != 0)
		{
			return distance * 0.02f * (10f + weight * (float)amount / 1000f);
		}
		if ((flags & StorageTransferFlags.Transport) != 0)
		{
			return distance * 0.002f * weight * (float)(10 + amount / 10000);
		}
		return distance * 0.002f * (10f + weight * (float)amount / 1000f);
	}
```

- `public static GetTransportCost(System.Single distance, System.Int32 amount, System.Single weight, Game.Companies.StorageTransferFlags flags) : System.Single`  

```csharp
public static float GetTransportCost(float distance, int amount, float weight, StorageTransferFlags flags)
	{
		if ((flags & StorageTransferFlags.Car) != 0)
		{
			return distance * 0.02f * (10f + weight * (float)amount / 1000f);
		}
		if ((flags & StorageTransferFlags.Transport) != 0)
		{
			return distance * 0.002f * weight * (float)(10 + amount / 10000);
		}
		return distance * 0.002f * (10f + weight * (float)amount / 1000f);
	}
```

- `public static GetWeight(Unity.Entities.EntityManager entityManager, Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs) : System.Single`  

```csharp
public static float GetWeight(Resource r, ResourcePrefabs prefabs, ref ComponentLookup<ResourceData> datas)
	{
		if (r == Resource.NoResource || r == Resource.All || r == Resource.Last)
		{
			return 0f;
		}
		Entity entity = prefabs[r];
		if (!datas.TryGetComponent(entity, out var componentData))
		{
			return 1f;
		}
		return componentData.m_Weight;
	}
```

- `public static GetWeight(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas) : System.Single`  

```csharp
public static float GetWeight(Resource r, ResourcePrefabs prefabs, ref ComponentLookup<ResourceData> datas)
	{
		if (r == Resource.NoResource || r == Resource.All || r == Resource.Last)
		{
			return 0f;
		}
		Entity entity = prefabs[r];
		if (!datas.TryGetComponent(entity, out var componentData))
		{
			return 1f;
		}
		return componentData.m_Weight;
	}
```

- `public static GetWorkerWorkforce(System.Int32 happiness, System.Int32 level) : System.Single`  

```csharp
public static float GetWorkerWorkforce(int happiness, int level)
	{
		return (((level == 0) ? 2f : 1f) + 2.5f * (float)level) * (0.75f + (float)happiness / 200f);
	}
```

- `public static GetWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Single`  

```csharp
public static float GetWorkforce(DynamicBuffer<Employee> employees, ref ComponentLookup<Citizen> citizens)
	{
		float num = 0f;
		for (int i = 0; i < employees.Length; i++)
		{
			if (citizens.HasComponent(employees[i].m_Worker))
			{
				Employee employee = employees[i];
				num += GetWorkerWorkforce(citizens[employee.m_Worker].Happiness, employee.m_Level);
			}
		}
		return num;
	}
```

- `public static IsCommercialResource(Game.Economy.Resource resource) : System.Boolean`  

```csharp
public static bool IsCommercialResource(Resource resource)
	{
		return (resource & (Resource)428424367916uL) != 0;
	}
```

- `public static IsExtractorResource(Game.Economy.Resource resource) : System.Boolean`  

```csharp
public static bool IsExtractorResource(Resource resource)
	{
		return (resource & (Resource)1099574706258uL) != 0;
	}
```

- `public static IsIndustrialResource(Game.Prefabs.ResourceData resourceData, System.Boolean includeMaterial, System.Boolean includeOffice) : System.Boolean`  

```csharp
public static bool IsIndustrialResource(ResourceData resourceData, bool includeMaterial, bool includeOffice)
	{
		if (resourceData.m_IsProduceable && includeMaterial == resourceData.m_IsMaterial)
		{
			return includeOffice == (resourceData.m_Weight == 0f);
		}
		return false;
	}
```

- `public static IsMaterial(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas) : System.Boolean`  

```csharp
public static bool IsMaterial(Resource r, ResourcePrefabs prefabs, ref ComponentLookup<ResourceData> datas)
	{
		return GetWeight(r, prefabs, ref datas) > 0f;
	}
```

- `public static IsOfficeResource(Game.Economy.Resource resource) : System.Boolean`  

```csharp
public static bool IsOfficeResource(Resource resource)
	{
		return (resource & (Resource)120261181440uL) != 0;
	}
```

- `public static IsProducedFrom(Game.Economy.Resource product, Game.Economy.Resource material) : System.Boolean`  

```csharp
public static bool IsProducedFrom(Resource product, Resource material)
	{
		return material switch
		{
			Resource.Grain => (product & (Resource)4295032844uL) != 0, 
			Resource.Wood => (product & Resource.Timber) != 0, 
			Resource.Oil => (product & Resource.Petrochemicals) != 0, 
			Resource.Ore => (product & Resource.Metals) != 0, 
			Resource.Petrochemicals => (product & (Resource)1074003968uL) != 0, 
			Resource.Plastics => (product & (Resource)1049600uL) != 0, 
			Resource.Electronics => (product & (Resource)17181966336uL) != 0, 
			Resource.Metals => (product & (Resource)536871936uL) != 0, 
			Resource.Coal => (product & Resource.Steel) != 0, 
			Resource.Stone => (product & (Resource)402653184uL) != 0, 
			Resource.Cotton => (product & Resource.Textiles) != 0, 
			Resource.Livestock => (product & (Resource)8589934604uL) != 0, 
			Resource.Vegetables => (product & (Resource)4294967304uL) != 0, 
			Resource.Steel => (product & Resource.Machinery) != 0, 
			Resource.Minerals => (product & (Resource)1074790400uL) != 0, 
			Resource.Chemicals => (product & (Resource)2147483904uL) != 0, 
			Resource.Timber => (product & Resource.Furniture) != 0, 
			Resource.Software => (product & (Resource)120259084288uL) != 0, 
			Resource.Food => (product & (Resource)2080uL) != 0, 
			Resource.Beverages => (product & (Resource)137438955552uL) != 0, 
			Resource.Fish => (product & (Resource)12uL) != 0, 
			_ => false, 
		};
	}
```

- `public static SetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, System.Int32 amount) : System.Void`  

```csharp
public static void SetResources(Resource resource, DynamicBuffer<Resources> resources, int amount)
	{
		for (int i = 0; i < resources.Length; i++)
		{
			Resources value = resources[i];
			if (value.m_Resource == resource)
			{
				value.m_Amount = amount;
				resources[i] = value;
				return;
			}
		}
		resources.Add(new Resources
		{
			m_Resource = resource,
			m_Amount = amount
		});
	}
```

- `public static SetTradeCost(Game.Economy.Resource resource, Game.Companies.TradeCost newcost, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs, System.Boolean keepLastTime, System.Single buyLerp = 1, System.Single sellLerp = 1) : System.Void`  

```csharp
public static void SetTradeCost(Resource resource, TradeCost newcost, DynamicBuffer<TradeCost> costs, bool keepLastTime, float buyLerp = 1f, float sellLerp = 1f)
	{
		Assert.IsTrue(!float.IsNaN(newcost.m_SellCost));
		Assert.IsTrue(!float.IsNaN(newcost.m_BuyCost));
		for (int i = 0; i < costs.Length; i++)
		{
			TradeCost tradeCost = costs[i];
			if (tradeCost.m_Resource == resource)
			{
				if (keepLastTime)
				{
					newcost.m_LastTransferRequestTime = tradeCost.m_LastTransferRequestTime;
				}
				newcost.m_BuyCost = ((tradeCost.m_BuyCost == 0f) ? newcost.m_BuyCost : math.lerp(tradeCost.m_BuyCost, newcost.m_BuyCost, buyLerp));
				newcost.m_SellCost = ((tradeCost.m_SellCost == 0f) ? newcost.m_SellCost : math.lerp(tradeCost.m_SellCost, newcost.m_SellCost, sellLerp));
				costs[i] = newcost;
				return;
			}
		}
		costs.Add(newcost);
	}
```


