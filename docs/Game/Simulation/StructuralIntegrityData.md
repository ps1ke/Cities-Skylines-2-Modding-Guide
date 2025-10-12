# Game.Simulation.EventHelpers+StructuralIntegrityData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.DestructibleObjectData> m_PrefabDestructibleObjectData`  
- `public Game.Prefabs.FireConfigurationData m_FireConfigurationData`  

## Constructors

- `public StructuralIntegrityData(Unity.Entities.SystemBase system)`  

## Methods

- `public GetStructuralIntegrity(Unity.Entities.Entity prefab, System.Boolean isBuilding) : System.Single`  
- `public Update(Unity.Entities.SystemBase system, Game.Prefabs.FireConfigurationData fireConfigurationData) : System.Void`  

