# Game.Prefabs.StatisticsData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct StatisticsData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Category;
    public Unity.Entities.Entity m_Group;
    public Game.City.StatisticType m_StatisticType;
    public Game.City.StatisticCollectionType m_CollectionType;
    public Game.City.StatisticUnitType m_UnitType;
    public UnityEngine.Color m_Color;
    public System.Boolean m_Stacked;

}
```


## Fields

- `public Unity.Entities.Entity m_Category`  

```csharp
public Unity.Entities.Entity m_Category;
```

- `public Unity.Entities.Entity m_Group`  

```csharp
public Unity.Entities.Entity m_Group;
```

- `public Game.City.StatisticType m_StatisticType`  

```csharp
public Game.City.StatisticType m_StatisticType;
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


