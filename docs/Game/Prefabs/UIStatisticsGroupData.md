# Game.Prefabs.UIStatisticsGroupData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct UIStatisticsGroupData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Category;
    public UnityEngine.Color m_Color;
    public Game.City.StatisticUnitType m_UnitType;
    public System.Boolean m_Stacked;

}
```


## Fields

- `public Unity.Entities.Entity m_Category`  

```csharp
public Unity.Entities.Entity m_Category;
```

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public Game.City.StatisticUnitType m_UnitType`  

```csharp
public Game.City.StatisticUnitType m_UnitType;
```

- `public System.Boolean m_Stacked`  

```csharp
public System.Boolean m_Stacked;
```


