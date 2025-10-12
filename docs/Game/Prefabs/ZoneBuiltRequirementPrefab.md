# Game.Prefabs.ZoneBuiltRequirementPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UnlockRequirementPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.ThemePrefab m_RequiredTheme`  
- `public Game.Prefabs.ZonePrefab m_RequiredZone`  
- `public Game.Zones.AreaType m_RequiredType`  
- `public System.Int32 m_MinimumSquares`  
- `public System.Int32 m_MinimumCount`  
- `public System.Int32 m_MinimumLevel`  

## Constructors

- `public ZoneBuiltRequirementPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

