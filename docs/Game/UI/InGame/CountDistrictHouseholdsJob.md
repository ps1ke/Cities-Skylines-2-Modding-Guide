# Game.UI.InGame.ResidentsSection+CountDistrictHouseholdsJob

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
- `public Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkLookup`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedLookup`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemLookup`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.TravelPurpose> m_TravelPurposeLookup`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_PropertyDataLookup`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdLookup`  
- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenLookup`  
- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdAnimal> m_HouseholdAnimalLookup`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterLookup`  
- `public Unity.Collections.NativeArray<System.Int32> m_Results`  
- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_HouseholdsResult`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

