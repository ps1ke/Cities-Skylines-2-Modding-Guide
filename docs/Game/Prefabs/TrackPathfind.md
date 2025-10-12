# Game.Prefabs.TrackPathfind

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.PathfindCostInfo m_DrivingCost`  
- `public Game.Prefabs.PathfindCostInfo m_TwowayCost`  
- `public Game.Prefabs.PathfindCostInfo m_SwitchCost`  
- `public Game.Prefabs.PathfindCostInfo m_DiamondCrossingCost`  
- `public Game.Prefabs.PathfindCostInfo m_CurveAngleCost`  
- `public Game.Prefabs.PathfindCostInfo m_SpawnCost`  

## Constructors

- `public TrackPathfind()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

