# Game.Pathfind.PathUpdated

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct PathUpdated : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Owner;
    public Game.Pathfind.PathEventData m_Data;

    public PathUpdated(Unity.Entities.Entity owner, Game.Pathfind.PathEventData data);

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

- `public PathUpdated(Unity.Entities.Entity owner, Game.Pathfind.PathEventData data)`  

```csharp
public PathUpdated(Entity owner, PathEventData data)
	{
		m_Owner = owner;
		m_Data = data;
	}
```


