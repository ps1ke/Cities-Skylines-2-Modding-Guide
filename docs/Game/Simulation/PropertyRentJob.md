# Game.Simulation.PropertyProcessingSystem+PropertyRentJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityArchetype m_RentEventArchetype`  
- `public Unity.Entities.EntityArchetype m_MovedEventArchetype`  
- `public Unity.Entities.ComponentLookup<Game.Companies.WorkProvider> m_WorkProviders`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ParkData> m_ParkDatas`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertiesOnMarket`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefs`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDatas`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDatas`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneDatas`  
- `public Unity.Entities.ComponentLookup<Game.Companies.CompanyData> m_Companies`  
- `public Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> m_Commercials`  
- `public Unity.Entities.ComponentLookup<Game.Companies.IndustrialCompany> m_Industrials`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas`  
- `public Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanyDatas`  
- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_Abandoneds`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_Parks`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> m_HomelessHouseholds`  
- `public Unity.Entities.BufferLookup<Game.Companies.Employee> m_Employees`  
- `public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreaBufs`  
- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  
- `public Unity.Entities.ComponentLookup<Game.Areas.Lot> m_Lots`  
- `public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_Geometries`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attacheds`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorCompanyData> m_ExtractorCompanyDatas`  
- `public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_Resources`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_Households`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renters`  
- `public Unity.Entities.EntityCommandBuffer m_CommandBuffer`  
- `public Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue`  
- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_ReservedProperties`  
- `public Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> m_TriggerQueue`  
- `public Unity.Collections.NativeQueue<Game.City.StatisticsEvent> m_StatisticsQueue`  
- `public System.Boolean m_DebugDisableHomeless`  

## Methods

- `public Execute() : System.Void`  

