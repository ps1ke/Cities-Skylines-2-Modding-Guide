# Game.Prefabs.PathfindTransportData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct PathfindTransportData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Pathfind.PathfindCosts m_OrderingCost;
    public Game.Pathfind.PathfindCosts m_StartingCost;
    public Game.Pathfind.PathfindCosts m_TravelCost;

}
```


## Fields

- `public Game.Pathfind.PathfindCosts m_OrderingCost`  

```csharp
public Game.Pathfind.PathfindCosts m_OrderingCost;
```

- `public Game.Pathfind.PathfindCosts m_StartingCost`  

```csharp
public Game.Pathfind.PathfindCosts m_StartingCost;
```

- `public Game.Pathfind.PathfindCosts m_TravelCost`  

```csharp
public Game.Pathfind.PathfindCosts m_TravelCost;
```


