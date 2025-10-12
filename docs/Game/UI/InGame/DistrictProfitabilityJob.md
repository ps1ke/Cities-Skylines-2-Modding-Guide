# Game.UI.InGame.ProfitabilitySection+DistrictProfitabilityJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.Entity m_SelectedEntity`  
- `public Unity.Entities.EntityTypeHandle m_EntityHandle`  
- `public Unity.Entities.ComponentTypeHandle<Game.Areas.CurrentDistrict> m_CurrentDistrictHandle`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefHandle`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Companies.CompanyData> m_CompanyDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedFromEntity`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Companies.Profitability> m_ProfitabilityFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.OfficeBuilding> m_OfficeBuildingFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Companies.WorkProvider> m_WorkProviderFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Companies.ServiceAvailable> m_ServiceAvailableFromEntity`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencyFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> m_WorkplaceDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZonePropertiesData> m_ZonePropertyDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanyDataFromEntity`  
- `public Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_ResourceAvailabilityFromEntity`  
- `public Unity.Entities.BufferLookup<Game.Companies.TradeCost> m_TradeCostFromEntity`  
- `public Unity.Entities.BufferLookup<Game.Companies.Employee> m_EmployeeFromEntity`  
- `public Game.Prefabs.EconomyParameterData m_EconomyParameters`  
- `public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  
- `public Unity.Collections.NativeArray<System.Int32> m_TaxRates`  
- `public Unity.Collections.NativeArray<Unity.Entities.Entity> m_Processes`  
- `public Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors`  
- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

