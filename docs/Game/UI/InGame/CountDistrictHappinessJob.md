# Game.UI.InGame.AverageHappinessSection+CountDistrictHappinessJob

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
- `public Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_AbandonedFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Household> m_HouseholdFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemFromEntity`  
- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenFromEntity`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_RenterFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDataFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.ElectricityConsumer> m_ElectricityConsumerFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.WaterConsumer> m_WaterConsumerFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.Locked> m_LockedFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.GarbageProducer> m_GarbageProducersFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.CrimeProducer> m_CrimeProducersFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.MailProducer> m_MailProducerFromEntity`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDataFromEntity`  
- `public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifierFromEntity`  
- `public Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverageFromEntity`  
- `public Game.Prefabs.CitizenHappinessParameterData m_CitizenHappinessParameters`  
- `public Game.Prefabs.GarbageParameterData m_GarbageParameters`  
- `public Game.Prefabs.HealthcareParameterData m_HealthcareParameters`  
- `public Game.Prefabs.ParkParameterData m_ParkParameters`  
- `public Game.Prefabs.EducationParameterData m_EducationParameters`  
- `public Game.Prefabs.TelecomParameterData m_TelecomParameters`  
- `public Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> m_HappinessFactorParameters`  
- `public Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> m_TelecomCoverage`  
- `public Unity.Collections.NativeArray<Game.Simulation.GroundPollution> m_PollutionMap`  
- `public Unity.Collections.NativeArray<Game.Simulation.NoisePollution> m_NoisePollutionMap`  
- `public Unity.Collections.NativeArray<Game.Simulation.AirPollution> m_AirPollutionMap`  
- `public Unity.Collections.NativeArray<System.Int32> m_TaxRates`  
- `public Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors`  
- `public Unity.Collections.NativeArray<System.Int32> m_Results`  
- `public Unity.Entities.Entity m_City`  
- `public System.Single m_RelativeElectricityFee`  
- `public System.Single m_RelativeWaterFee`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

