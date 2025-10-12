# Game.Simulation.EventHelpers+FireHazardData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Game.Buildings.LocalEffectSystem+ReadData m_LocalEffectData`  
- `public System.Single m_ForestFireHazardFactor`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.DestructibleObjectData> m_PrefabDestructibleObjectData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData`  
- `public Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverages`  
- `public Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> m_DistrictModifiers`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZonePropertiesData> m_ZonePropertiesData`  

## Constructors

- `public FireHazardData(Unity.Entities.SystemBase system)`  

## Methods

- `public GetFireHazard(Game.Prefabs.PrefabRef prefabRef, Game.Buildings.Building building, Game.Areas.CurrentDistrict currentDistrict, Game.Objects.Damaged damaged, Game.Objects.UnderConstruction underConstruction, System.Single& fireHazard, System.Single& riskFactor) : System.Boolean`  
- `public GetFireHazard(Game.Prefabs.PrefabRef prefabRef, Game.Objects.Tree tree, Game.Objects.Transform transform, Game.Objects.Damaged damaged, System.Single& fireHazard, System.Single& riskFactor) : System.Boolean`  
- `private GetFireHazard(Game.Prefabs.PrefabRef prefabRef) : System.Single`  
- `private GetFireHazardFactor(Game.Objects.Damaged damaged) : System.Single`  
- `public Update(Unity.Entities.SystemBase system, Game.Buildings.LocalEffectSystem+ReadData localEffectData, Game.Prefabs.FireConfigurationPrefab fireConfigurationPrefab, System.Single temperature, System.Single noRainDays) : System.Void`  

