# Game.Pathfind.SetupQueueItem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SetupQueueItem
{
    public Unity.Entities.Entity m_Owner;
    public Game.Pathfind.PathfindParameters m_Parameters;
    public Game.Pathfind.SetupQueueTarget m_Origin;
    public Game.Pathfind.SetupQueueTarget m_Destination;

    public SetupQueueItem(Unity.Entities.Entity owner, Game.Pathfind.PathfindParameters parameters, Game.Pathfind.SetupQueueTarget origin, Game.Pathfind.SetupQueueTarget destination);

}
```


## Fields

- `public Unity.Entities.Entity m_Owner`  

```csharp
public Unity.Entities.Entity m_Owner;
```

- `public Game.Pathfind.PathfindParameters m_Parameters`  

```csharp
public Game.Pathfind.PathfindParameters m_Parameters;
```

- `public Game.Pathfind.SetupQueueTarget m_Origin`  

```csharp
public Game.Pathfind.SetupQueueTarget m_Origin;
```

- `public Game.Pathfind.SetupQueueTarget m_Destination`  

```csharp
public Game.Pathfind.SetupQueueTarget m_Destination;
```


## Constructors

- `public SetupQueueItem(Unity.Entities.Entity owner, Game.Pathfind.PathfindParameters parameters, Game.Pathfind.SetupQueueTarget origin, Game.Pathfind.SetupQueueTarget destination)`  

```csharp
public SetupQueueItem(Entity owner, PathfindParameters parameters, SetupQueueTarget origin, SetupQueueTarget destination)
	{
		m_Owner = owner;
		m_Parameters = parameters;
		m_Origin = origin;
		m_Destination = destination;
	}
```


