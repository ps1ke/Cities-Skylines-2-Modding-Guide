# Game.Prefabs.PathfindTrackData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct PathfindTrackData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Pathfind.PathfindCosts m_DrivingCost;
    public Game.Pathfind.PathfindCosts m_TwowayCost;
    public Game.Pathfind.PathfindCosts m_SwitchCost;
    public Game.Pathfind.PathfindCosts m_DiamondCrossingCost;
    public Game.Pathfind.PathfindCosts m_CurveAngleCost;
    public Game.Pathfind.PathfindCosts m_SpawnCost;

}
```


## Fields

- `public Game.Pathfind.PathfindCosts m_DrivingCost`  

```csharp
public Game.Pathfind.PathfindCosts m_DrivingCost;
```

- `public Game.Pathfind.PathfindCosts m_TwowayCost`  

```csharp
public Game.Pathfind.PathfindCosts m_TwowayCost;
```

- `public Game.Pathfind.PathfindCosts m_SwitchCost`  

```csharp
public Game.Pathfind.PathfindCosts m_SwitchCost;
```

- `public Game.Pathfind.PathfindCosts m_DiamondCrossingCost`  

```csharp
public Game.Pathfind.PathfindCosts m_DiamondCrossingCost;
```

- `public Game.Pathfind.PathfindCosts m_CurveAngleCost`  

```csharp
public Game.Pathfind.PathfindCosts m_CurveAngleCost;
```

- `public Game.Pathfind.PathfindCosts m_SpawnCost`  

```csharp
public Game.Pathfind.PathfindCosts m_SpawnCost;
```


