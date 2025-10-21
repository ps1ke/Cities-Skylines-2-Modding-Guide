# Game.Pathfind.CoverageUpdated

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct CoverageUpdated : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Owner;
    public Game.Pathfind.PathEventData m_Data;

    public CoverageUpdated(Unity.Entities.Entity owner, Game.Pathfind.PathEventData data);

}
```


## Fields

- `public Unity.Entities.Entity m_Owner`  

```csharp
public Unity.Entities.Entity m_Owner;
```

- `public Game.Pathfind.PathEventData m_Data`  

```csharp
public Game.Pathfind.PathEventData m_Data;
```


## Constructors

- `public CoverageUpdated(Unity.Entities.Entity owner, Game.Pathfind.PathEventData data)`  

```csharp
public CoverageUpdated(Unity.Entities.Entity owner, Game.Pathfind.PathEventData data);
```


