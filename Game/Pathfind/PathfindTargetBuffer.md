# Game.Pathfind.PathfindTargetBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Game.Pathfind.IPathfindTargetBuffer`  

## Code

```csharp
public sealed struct PathfindTargetBuffer : Game.Pathfind.IPathfindTargetBuffer
{
    private Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Queue;

    public System.Void Enqueue(Game.Pathfind.PathTarget pathTarget);
}
```


## Fields

- `private Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Queue`  

```csharp
private Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Queue;
```


## Methods

- `public Enqueue(Game.Pathfind.PathTarget pathTarget) : System.Void`  

```csharp
public void Enqueue(PathTarget pathTarget)
	{
		m_Queue.Enqueue(pathTarget);
	}
```


