# Game.Prefabs.BuildingProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Int32 m_ResidentialProperties`  
- `public Game.Economy.ResourceInEditor[] m_AllowedSold`  
- `public Game.Economy.ResourceInEditor[] m_AllowedInput`  
- `public Game.Economy.ResourceInEditor[] m_AllowedManufactured`  
- `public Game.Economy.ResourceInEditor[] m_AllowedStored`  
- `public System.Single m_SpaceMultiplier`  

## Constructors

- `public BuildingProperties()`  

## Methods

- `public static AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPropertyData propertyData) : System.Void`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetPropertyData() : Game.Prefabs.BuildingPropertyData`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

