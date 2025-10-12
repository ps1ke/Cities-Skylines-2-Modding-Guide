# Game.Prefabs.CarPathfind

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.PathfindCostInfo m_DrivingCost`  
- `public Game.Prefabs.PathfindCostInfo m_TurningCost`  
- `public Game.Prefabs.PathfindCostInfo m_UTurnCost`  
- `public Game.Prefabs.PathfindCostInfo m_UnsafeUTurnCost`  
- `public Game.Prefabs.PathfindCostInfo m_CurveAngleCost`  
- `public Game.Prefabs.PathfindCostInfo m_LaneCrossCost`  
- `public Game.Prefabs.PathfindCostInfo m_ParkingCost`  
- `public Game.Prefabs.PathfindCostInfo m_SpawnCost`  
- `public Game.Prefabs.PathfindCostInfo m_ForbiddenCost`  

## Constructors

- `public CarPathfind()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

