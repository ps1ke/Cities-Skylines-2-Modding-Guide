# Game.Simulation.CommercialFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_CommerceQuery`  
- `private Unity.Entities.EntityQuery m_FreePropertyQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_ZonePreferenceQuery`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.CommercialFindPropertySystem+TypeHandle __TypeHandle`  

## Constructors

- `public CommercialFindPropertySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterBuffers, Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> companies, Game.Prefabs.ZonePreferenceData& preferences) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CommercialFindPropertySystem+TypeHandle`  

