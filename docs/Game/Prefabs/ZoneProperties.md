# Game.Prefabs.ZoneProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IZoneBuildingComponent`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Boolean m_ScaleResidentials`  
- `public System.Single m_ResidentialProperties`  
- `public System.Single m_SpaceMultiplier`  
- `public Game.Economy.ResourceInEditor[] m_AllowedSold`  
- `public Game.Economy.ResourceInEditor[] m_AllowedInput`  
- `public Game.Economy.ResourceInEditor[] m_AllowedManufactured`  
- `public Game.Economy.ResourceInEditor[] m_AllowedStored`  
- `public System.Single m_FireHazardMultiplier`  
- `public System.Boolean m_IgnoreLandValue`  

## Constructors

- `public ZoneProperties()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  
- `public GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  
- `private GetBuildingPropertyData(Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : Game.Prefabs.BuildingPropertyData`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

