# Game.Simulation.IndustrialFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  
- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  
- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Unity.Entities.EntityQuery m_IndustryQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorQuery`  
- `private Unity.Entities.EntityQuery m_FreePropertyQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_ZonePreferenceQuery`  
- `private Unity.Entities.EntityQuery m_FreeExtractorQuery`  
- `private Unity.Entities.EntityQuery m_CompanyPrefabQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  
- `private Game.Simulation.IndustrialFindPropertySystem+TypeHandle __TypeHandle`  

## Constructors

- `public IndustrialFindPropertySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> propertiesOnMarket, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> workplaceDatas, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.EconomyParameterData economyParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, System.Boolean storage) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.IndustrialFindPropertySystem+TypeHandle`  

