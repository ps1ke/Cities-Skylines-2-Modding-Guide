# Game.Prefabs.StatisticsPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ArchetypePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class StatisticsPrefab : Game.Prefabs.ArchetypePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.UIStatisticsCategoryPrefab m_Category;
    public Game.Prefabs.UIStatisticsGroupPrefab m_Group;
    public Game.City.StatisticType m_StatisticsType;
    public Game.City.StatisticCollectionType m_CollectionType;
    public Game.City.StatisticUnitType m_UnitType;
    public UnityEngine.Color m_Color;
    public System.Boolean m_Stacked;

    public StatisticsPrefab();

    public static Unity.Entities.Entity CreateInstance(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.ArchetypeData archetypeData, System.Int32 parameter);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.UIStatisticsCategoryPrefab m_Category`  

```csharp
public Game.Prefabs.UIStatisticsCategoryPrefab m_Category;
```

- `public Game.Prefabs.UIStatisticsGroupPrefab m_Group`  

```csharp
public Game.Prefabs.UIStatisticsGroupPrefab m_Group;
```

- `public Game.City.StatisticType m_StatisticsType`  

```csharp
public Game.City.StatisticType m_StatisticsType;
```

- `public Game.City.StatisticCollectionType m_CollectionType`  

```csharp
public Game.City.StatisticCollectionType m_CollectionType;
```

- `public Game.City.StatisticUnitType m_UnitType`  

```csharp
public Game.City.StatisticUnitType m_UnitType;
```

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public System.Boolean m_Stacked`  

```csharp
public System.Boolean m_Stacked;
```


## Constructors

- `public StatisticsPrefab()`  

```csharp
public StatisticsPrefab();
```


## Methods

- `public static CreateInstance(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.ArchetypeData archetypeData, System.Int32 parameter = 0) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity CreateInstance(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.ArchetypeData archetypeData, System.Int32 parameter);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


