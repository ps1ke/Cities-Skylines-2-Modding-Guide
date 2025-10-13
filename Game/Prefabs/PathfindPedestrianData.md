# Game.Prefabs.PathfindPedestrianData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct PathfindPedestrianData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Pathfind.PathfindCosts m_WalkingCost;
    public Game.Pathfind.PathfindCosts m_CrosswalkCost;
    public Game.Pathfind.PathfindCosts m_UnsafeCrosswalkCost;
    public Game.Pathfind.PathfindCosts m_SpawnCost;

}
```


## Fields

- `public Game.Pathfind.PathfindCosts m_WalkingCost`  

```csharp
public Game.Pathfind.PathfindCosts m_WalkingCost;
```

- `public Game.Pathfind.PathfindCosts m_CrosswalkCost`  

```csharp
public Game.Pathfind.PathfindCosts m_CrosswalkCost;
```

- `public Game.Pathfind.PathfindCosts m_UnsafeCrosswalkCost`  

```csharp
public Game.Pathfind.PathfindCosts m_UnsafeCrosswalkCost;
```

- `public Game.Pathfind.PathfindCosts m_SpawnCost`  

```csharp
public Game.Pathfind.PathfindCosts m_SpawnCost;
```


