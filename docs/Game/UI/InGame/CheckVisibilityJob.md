# Game.UI.InGame.HouseholdSidebarSection+CheckVisibilityJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.Entity m_SelectedEntity`  
- `public Unity.Entities.Entity m_SelectedPrefab`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingLookup`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkFromLookup`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenLookup`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.HouseholdPet> m_HouseholdPetLookup`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup`  
- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup`  
- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

## Methods

- `public Execute() : System.Void`  
- `private HasResidentialProperties(System.Int32& residentCount, System.Int32& householdCount, Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

