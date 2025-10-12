# Game.Economy.EconomyUtils

**Assembly:** `Game`  
**Namespace:** `Game.Economy`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `public static readonly System.Int32 kCompanyUpdatesPerDay`  
- `public static readonly System.Int32 ResourceCount`  

## Constructors

- `public EconomyUtils()`  

## Methods

- `public static AddResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  
- `public static AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> from, Unity.Entities.DynamicBuffer<Game.Economy.Resources> to) : System.Void`  
- `public static BuildPseudoTradeCost(System.Single distance, Game.Prefabs.IndustrialProcessData process, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.ResourcePrefabs resourcePrefabs) : Unity.Mathematics.float3`  
- `public static CalculateNumberOfWorkplaces(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel) : Game.Companies.Workplaces`  
- `public static CalculateTotalWage(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.EconomyParameterData& econParams) : System.Int32`  
- `public static CalculateTotalWage(System.Int32 totalWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel, Game.Prefabs.EconomyParameterData econParams) : System.Int32`  
- `public static CountResources(Game.Economy.Resource resource) : System.Int32`  
- `public static GetAllResources() : Game.Economy.Resource`  
- `public static GetAvailableResourceSupply(Game.Economy.Resource resource) : Game.Net.AvailableResource`  
- `public static GetAverageWorkforce(System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 buildingLevel) : System.Single`  
- `public static GetAverageWorkforce(Game.Companies.Workplaces workplaces) : System.Single`  
- `public static GetAverageWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees) : System.Single`  
- `public static GetCompanyMaxProfitPerDay(Game.Companies.WorkProvider workProvider, System.Boolean isIndustrial, System.Int32 level, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.WorkplaceData workplaceData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  
- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  
- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  
- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  
- `public static GetCompanyProductionPerDay(System.Single buildingEfficiency, System.Int32 workerAmount, System.Int32 level, System.Boolean isIndustrial, Game.Prefabs.WorkplaceData workplaceData, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourceData resourceData, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  
- `public static GetCompanyProfitPerDay(System.Single buildingEfficiency, System.Boolean isIndustrial, Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Game.Prefabs.EconomyParameterData& economyParameters) : System.Int32`  
- `public static GetCompanyProfitPerUnit(System.Boolean isIndustrial, Game.Prefabs.IndustrialProcessData processData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  
- `public static GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> vehicles, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layouts, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTrucks, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Int32`  
- `public static GetCompanyTotalWorth(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Int32`  
- `public static GetHouseholdIncome(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Collections.NativeArray<System.Int32> taxRates) : System.Int32`  
- `public static GetHouseholdSpendableMoney(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& m_RenterBufs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Game.Buildings.PropertyRenter propertyRenter) : System.Int32`  
- `public static GetHouseholdTotalWealth(Game.Citizens.Household householdData, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  
- `public static GetIncomeSource(Game.City.PlayerResource resource) : Game.City.IncomeSource`  
- `public static GetIndustrialPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  
- `public static GetLastTradeRequestTime(Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs) : System.Int64`  
- `public static GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  
- `public static GetMarketPrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.EntityManager entityManager) : System.Single`  
- `public static GetMarketPrice(Game.Prefabs.ResourceData data) : System.Single`  
- `public static GetName(Game.Economy.Resource r) : System.String`  
- `public static GetNameFixed(Game.Economy.Resource r) : Unity.Collections.FixedString32Bytes`  
- `public static GetNames(Game.Economy.Resource r) : System.String`  
- `public static GetProcessComplexity(Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_IndustrialProcessDataChunks, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Game.Economy.Resource r, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.IndustrialProcessData> processType, Game.Prefabs.WorkplaceComplexity& complexity) : System.Boolean`  
- `public static GetResource(Game.Economy.ResourceInEditor resource) : Game.Economy.Resource`  
- `public static GetResource(System.Int32 index) : Game.Economy.Resource`  
- `public static GetResource(Game.Net.AvailableResource available) : Game.Economy.Resource`  
- `public static GetResourceColor(Game.Economy.Resource r) : UnityEngine.Color`  
- `public static GetResourceIndex(Game.Economy.Resource r) : System.Int32`  
- `public static GetResources(Game.Economy.ResourceInEditor[] resources, Game.Economy.Resource defaultResources = NoResource) : Game.Economy.Resource`  
- `public static GetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  
- `public static GetServicePrice(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  
- `public static GetServicePriceMultiplier(System.Single serviceAvailable, System.Int32 maxServiceAvailable) : System.Single`  
- `public static GetTotalStorageUsed(Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources) : System.Int32`  
- `public static GetTradeCost(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs) : Game.Companies.TradeCost`  
- `public static GetTransportCost(System.Single distance, Game.Economy.Resource resource, System.Int32 amount, System.Single weight) : System.Int32`  
- `public static GetTransportCost(System.Single distance, System.Int32 amount, System.Single weight, Game.Companies.StorageTransferFlags flags) : System.Single`  
- `public static GetWeight(Unity.Entities.EntityManager entityManager, Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs) : System.Single`  
- `public static GetWeight(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas) : System.Single`  
- `public static GetWorkerWorkforce(System.Int32 happiness, System.Int32 level) : System.Single`  
- `public static GetWorkforce(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Single`  
- `public static IsCommercialResource(Game.Economy.Resource resource) : System.Boolean`  
- `public static IsExtractorResource(Game.Economy.Resource resource) : System.Boolean`  
- `public static IsIndustrialResource(Game.Prefabs.ResourceData resourceData, System.Boolean includeMaterial, System.Boolean includeOffice) : System.Boolean`  
- `public static IsMaterial(Game.Economy.Resource r, Game.Prefabs.ResourcePrefabs prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& datas) : System.Boolean`  
- `public static IsOfficeResource(Game.Economy.Resource resource) : System.Boolean`  
- `public static IsProducedFrom(Game.Economy.Resource product, Game.Economy.Resource material) : System.Boolean`  
- `public static SetResources(Game.Economy.Resource resource, Unity.Entities.DynamicBuffer<Game.Economy.Resources> resources, System.Int32 amount) : System.Void`  
- `public static SetTradeCost(Game.Economy.Resource resource, Game.Companies.TradeCost newcost, Unity.Entities.DynamicBuffer<Game.Companies.TradeCost> costs, System.Boolean keepLastTime, System.Single buyLerp = 1, System.Single sellLerp = 1) : System.Void`  

