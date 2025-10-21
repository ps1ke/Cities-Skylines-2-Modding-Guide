# Game.Prefabs.ServiceData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ServiceData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.City.CityService m_Service;
    public System.Boolean m_BudgetAdjustable;

}
```


## Fields

- `public Game.City.CityService m_Service`  

```csharp
public Game.City.CityService m_Service;
```

- `public System.Boolean m_BudgetAdjustable`  

```csharp
public System.Boolean m_BudgetAdjustable;
```


