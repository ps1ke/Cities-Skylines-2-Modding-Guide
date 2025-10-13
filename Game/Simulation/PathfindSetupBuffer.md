# Game.Simulation.PathfindSetupBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Game.Pathfind.IPathfindTargetBuffer`  

## Code

```csharp
public sealed struct PathfindSetupBuffer : Game.Pathfind.IPathfindTargetBuffer
{
    public Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> m_Queue;
    public System.Int32 m_SetupIndex;

    public System.Void Enqueue(Game.Pathfind.PathTarget pathTarget);
}
```


## Fields

- `public Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> m_Queue`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> m_Queue;
```

- `public System.Int32 m_SetupIndex`  

```csharp
public System.Int32 m_SetupIndex;
```


## Methods

- `public Enqueue(Game.Pathfind.PathTarget pathTarget) : System.Void`  

```csharp
public void Enqueue(PathTarget pathTarget)
	{
		m_Queue.Enqueue(new PathfindSetupTarget
		{
			m_SetupIndex = m_SetupIndex,
			m_PathTarget = pathTarget
		});
	}
```


