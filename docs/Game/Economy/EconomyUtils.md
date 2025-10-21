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
public static System.Int32 AddResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources);
```

- `public static AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> from, Unity.Entities.DynamicBuffer<Game.Economy.Resources> to) : System.Void`  

```csharp
public static System.Void AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> from, Unity.Entities.DynamicBuffer<Game.Economy.Resources> to);
```

- `public static BuildPseudoTradeCost(System.Single distance, Game.Prefabs.IndustrialProcessData process, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 BuildPseudoTradeCost(System.Single distance, Game.Prefabs.IndustrialProcessData process, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs);
```

- `public static CalculateNumberOfWorkplaces(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel) : Game.Companies.Workplaces`  

```csharp
public static Game.Companies.Workplaces CalculateNumberOfWorkplaces(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel);
```

- `public static CalculateTotalWage(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.EconomyParameterData& econParams) : System.Int32`  

```csharp
public static System.Int32 CalculateTotalWage(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.EconomyParameterData& econParams);
```

- `public static CalculateTotalWage(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel, Game.Prefabs.EconomyParameterData econParams) : System.Int32`  

```csharp
public static System.Int32 CalculateTotalWage(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel, Game.Prefabs.EconomyParameterData econParams);
```

- `public static CountResources(Game.Economy.Resource resource) : System.Int32`  

```csharp
public static System.Int32 CountResources(Game.Economy.Resource resource);
```

- `public static GetAllResources() : Game.Economy.Resource`  

```csharp
public static Game.Economy.Resource GetAllResources();
```

- `public static GetAvailableResourceSupply(Game.Economy.Resource resource) : Game.Net.AvailableResource`  

```csharp
public static Game.Net.AvailableResource GetAvailableResourceSupply(Game.Economy.Resource resource);
```

- `public static GetAverageWorkforce(System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel) : System.Single`  

```csharp
public static System.Single GetAverageWorkforce(System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel);
```

- `public static GetAverageWorkforce(Game.Companies.Workplaces workplaces) : System.Single`  

```csharp
public static System.Single GetAverageWorkforce(Game.Companies.Workplaces workplaces);
```

- `public static GetAverageWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees) : System.Single`  

```csharp
public static System.Single GetAverageWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees);
```

- `public static GetCompanyMaxProfitPerDay(Game.Companies.WorkProvider workProvider, System.Boolean isIndustrial, System.Int32 level, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.WorkplaceData workplaceData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static System.Int32 GetCompanyMaxProfitPerDay(Game.Companies.WorkProvider workProvider, System.Boolean isIndustrial, System.Int32 level, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.WorkplaceData workplaceData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static System.Int32 GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static System.Int32 GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static System.Int32 GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static System.Int32 GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public static GetCompanyProfitPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  

```csharp
public static System.Int32 GetCompanyProfitPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public static GetCompanyProfitPerUnit(System.Boolean isIndustrial, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static System.Single GetCompanyProfitPerUnit(System.Boolean isIndustrial, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
```

- `public static GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> vehicles, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layouts, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTrucks, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Int32`  

```csharp
public static System.Int32 GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> vehicles, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layouts, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTrucks, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
```

- `public static GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Int32`  

```csharp
public static System.Int32 GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
```

- `public static GetHouseholdIncome(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  

```csharp
public static System.Int32 GetHouseholdIncome(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Collections.NativeArray<System.Int32> taxRates);
```

- `public static GetHouseholdSpendableMoney(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_RenterBufs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Game.Buildings.PropertyRenter propertyRenter) : System.Int32`  

```csharp
public static System.Int32 GetHouseholdSpendableMoney(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_RenterBufs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Game.Buildings.PropertyRenter propertyRenter);
```

- `public static GetHouseholdTotalWealth(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  

```csharp
public static System.Int32 GetHouseholdTotalWealth(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources);
```

- `public static GetIncomeSource(Game.City.PlayerResource resource) : Game.City.IncomeSource`  

```csharp
public static Game.City.IncomeSource GetIncomeSource(Game.City.PlayerResource resource);
```

- `public static GetIndustrialPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static System.Single GetIndustrialPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
```

- `public static GetLastTradeRequestTime(Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs) : System.Int64`  

```csharp
public static System.Int64 GetLastTradeRequestTime(Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs);
```

- `public static GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static System.Single GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
```

- `public static GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.EntityManager entityManager) : System.Single`  

```csharp
public static System.Single GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.EntityManager entityManager);
```

- `public static GetMarketPrice(Game.Prefabs.ResourceData data) : System.Single`  

```csharp
public static System.Single GetMarketPrice(Game.Prefabs.ResourceData data);
```

- `public static GetName(Game.Economy.Resource r) : System.String`  

```csharp
public static System.String GetName(Game.Economy.Resource r);
```

- `public static GetNameFixed(Game.Economy.Resource r) : Unity.Collections.FixedString32Bytes`  

```csharp
public static Unity.Collections.FixedString32Bytes GetNameFixed(Game.Economy.Resource r);
```

- `public static GetNames(Game.Economy.Resource r) : System.String`  

```csharp
public static System.String GetNames(Game.Economy.Resource r);
```

- `public static GetProcessComplexity(Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_IndustrialProcessDataChunks, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Game.Economy.Resource r, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.IndustrialProcessData> processType, Game.Prefabs.WorkplaceComplexity& complexity) : System.Boolean`  

```csharp
public static System.Boolean GetProcessComplexity(Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_IndustrialProcessDataChunks, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Game.Economy.Resource r, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.IndustrialProcessData> processType, Game.Prefabs.WorkplaceComplexity& complexity);
```

- `public static GetResource(Game.Economy.ResourceInEditor resource) : Game.Economy.Resource`  

```csharp
public static Game.Economy.Resource GetResource(Game.Economy.ResourceInEditor resource);
```

- `public static GetResource(System.Int32 index) : Game.Economy.Resource`  

```csharp
public static Game.Economy.Resource GetResource(System.Int32 index);
```

- `public static GetResource(Game.Net.AvailableResource available) : Game.Economy.Resource`  

```csharp
public static Game.Economy.Resource GetResource(Game.Net.AvailableResource available);
```

- `public static GetResourceColor(Game.Economy.Resource r) : UnityEngine.Color`  

```csharp
public static UnityEngine.Color GetResourceColor(Game.Economy.Resource r);
```

- `public static GetResourceIndex(Game.Economy.Resource r) : System.Int32`  

```csharp
public static System.Int32 GetResourceIndex(Game.Economy.Resource r);
```

- `public static GetResources(Game.Economy.ResourceInEditor[] resources, Game.Economy.Resource defaultResources = NoResource) : Game.Economy.Resource`  

```csharp
public static Game.Economy.Resource GetResources(Game.Economy.ResourceInEditor[] resources, Game.Economy.Resource defaultResources);
```

- `public static GetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  

```csharp
public static System.Int32 GetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources);
```

- `public static GetServicePrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static System.Single GetServicePrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
```

- `public static GetServicePriceMultiplier(System.Single serviceAvailable, System.Int32 maxServiceAvailable) : System.Single`  

```csharp
public static System.Single GetServicePriceMultiplier(System.Single serviceAvailable, System.Int32 maxServiceAvailable);
```

- `public static GetTotalStorageUsed(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  

```csharp
public static System.Int32 GetTotalStorageUsed(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources);
```

- `public static GetTradeCost(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs) : Game.Companies.TradeCost`  

```csharp
public static Game.Companies.TradeCost GetTradeCost(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs);
```

- `public static GetTransportCost(System.Single distance, Game.Economy.Resource resource, System.Int32 amount, System.Single weight) : System.Int32`  

```csharp
public static System.Int32 GetTransportCost(System.Single distance, Game.Economy.Resource resource, System.Int32 amount, System.Single weight);
```

- `public static GetTransportCost(System.Single distance, System.Int32 amount, System.Single weight, Game.Companies.StorageTransferFlags flags) : System.Single`  

```csharp
public static System.Single GetTransportCost(System.Single distance, System.Int32 amount, System.Single weight, Game.Companies.StorageTransferFlags flags);
```

- `public static GetWeight(Unity.Entities.EntityManager entityManager, Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs) : System.Single`  

```csharp
public static System.Single GetWeight(Unity.Entities.EntityManager entityManager, Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs);
```

- `public static GetWeight(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas) : System.Single`  

```csharp
public static System.Single GetWeight(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas);
```

- `public static GetWorkerWorkforce(System.Int32 happiness, System.Int32 level) : System.Single`  

```csharp
public static System.Single GetWorkerWorkforce(System.Int32 happiness, System.Int32 level);
```

- `public static GetWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Single`  

```csharp
public static System.Single GetWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
```

- `public static IsCommercialResource(Game.Economy.Resource resource) : System.Boolean`  

```csharp
public static System.Boolean IsCommercialResource(Game.Economy.Resource resource);
```

- `public static IsExtractorResource(Game.Economy.Resource resource) : System.Boolean`  

```csharp
public static System.Boolean IsExtractorResource(Game.Economy.Resource resource);
```

- `public static IsIndustrialResource(Game.Prefabs.ResourceData resourceData, System.Boolean includeMaterial, System.Boolean includeOffice) : System.Boolean`  

```csharp
public static System.Boolean IsIndustrialResource(Game.Prefabs.ResourceData resourceData, System.Boolean includeMaterial, System.Boolean includeOffice);
```

- `public static IsMaterial(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas) : System.Boolean`  

```csharp
public static System.Boolean IsMaterial(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas);
```

- `public static IsOfficeResource(Game.Economy.Resource resource) : System.Boolean`  

```csharp
public static System.Boolean IsOfficeResource(Game.Economy.Resource resource);
```

- `public static IsProducedFrom(Game.Economy.Resource product, Game.Economy.Resource material) : System.Boolean`  

```csharp
public static System.Boolean IsProducedFrom(Game.Economy.Resource product, Game.Economy.Resource material);
```

- `public static SetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, System.Int32 amount) : System.Void`  

```csharp
public static System.Void SetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, System.Int32 amount);
```

- `public static SetTradeCost(Game.Economy.Resource resource, Game.Companies.TradeCost newcost, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs, System.Boolean keepLastTime, System.Single buyLerp = 1, System.Single sellLerp = 1) : System.Void`  

```csharp
public static System.Void SetTradeCost(Game.Economy.Resource resource, Game.Companies.TradeCost newcost, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs, System.Boolean keepLastTime, System.Single buyLerp, System.Single sellLerp);
```


