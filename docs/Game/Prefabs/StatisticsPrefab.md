# Game.Prefabs.StatisticsPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ArchetypePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.UIStatisticsCategoryPrefab m_Category`  
- `public Game.Prefabs.UIStatisticsGroupPrefab m_Group`  
- `public Game.City.StatisticType m_StatisticsType`  
- `public Game.City.StatisticCollectionType m_CollectionType`  
- `public Game.City.StatisticUnitType m_UnitType`  
- `public UnityEngine.Color m_Color`  
- `public System.Boolean m_Stacked`  

## Constructors

- `public StatisticsPrefab()`  

## Methods

- `public static CreateInstance(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.ArchetypeData archetypeData, System.Int32 parameter = 0) : Unity.Entities.Entity`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

