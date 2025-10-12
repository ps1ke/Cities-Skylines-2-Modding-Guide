# Game.Prefabs.ZonePollution

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IZoneBuildingComponent`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_GroundPollution`  
- `public System.Single m_AirPollution`  
- `public System.Single m_NoisePollution`  

## Constructors

- `public ZonePollution()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  
- `private GetBuildingPollutionData(Game.Prefabs.BuildingPrefab buildingPrefab) : Game.Prefabs.PollutionData`  
- `public GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

