# Game.Pathfind.PathTarget

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PathTarget
{
    public Unity.Entities.Entity m_Target;
    public Unity.Entities.Entity m_Entity;
    public System.Single m_Delta;
    public System.Single m_Cost;
    public Game.Pathfind.EdgeFlags m_Flags;

    public PathTarget(Unity.Entities.Entity target, Unity.Entities.Entity entity, System.Single delta, System.Single cost);
    public PathTarget(Unity.Entities.Entity target, Unity.Entities.Entity entity, System.Single delta, System.Single cost, Game.Pathfind.EdgeFlags flags);

}
```


## Fields

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public System.Single m_Delta`  

```csharp
public System.Single m_Delta;
```

- `public System.Single m_Cost`  

```csharp
public System.Single m_Cost;
```

- `public Game.Pathfind.EdgeFlags m_Flags`  

```csharp
public Game.Pathfind.EdgeFlags m_Flags;
```


## Constructors

- `public PathTarget(Unity.Entities.Entity target, Unity.Entities.Entity entity, System.Single delta, System.Single cost)`  

```csharp
public PathTarget(Entity target, Entity entity, float delta, float cost, EdgeFlags flags)
	{
		m_Target = target;
		m_Entity = entity;
		m_Delta = delta;
		m_Cost = cost;
		m_Flags = flags;
	}
```

- `public PathTarget(Unity.Entities.Entity target, Unity.Entities.Entity entity, System.Single delta, System.Single cost, Game.Pathfind.EdgeFlags flags)`  

```csharp
public PathTarget(Entity target, Entity entity, float delta, float cost, EdgeFlags flags)
	{
		m_Target = target;
		m_Entity = entity;
		m_Delta = delta;
		m_Cost = cost;
		m_Flags = flags;
	}
```


