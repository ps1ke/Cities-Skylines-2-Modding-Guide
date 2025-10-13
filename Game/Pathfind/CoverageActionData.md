# Game.Pathfind.CoverageActionData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct CoverageActionData : System.IDisposable
{
    public Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Sources;
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.CoverageResult> m_Results;
    public Game.Pathfind.CoverageParameters m_Parameters;
    public Game.Pathfind.PathfindActionState m_State;

    public CoverageActionData(Unity.Collections.Allocator allocator);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Sources`  

```csharp
public Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Sources;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.CoverageResult> m_Results`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.CoverageResult> m_Results;
```

- `public Game.Pathfind.CoverageParameters m_Parameters`  

```csharp
public Game.Pathfind.CoverageParameters m_Parameters;
```

- `public Game.Pathfind.PathfindActionState m_State`  

```csharp
public Game.Pathfind.PathfindActionState m_State;
```


## Constructors

- `public CoverageActionData(Unity.Collections.Allocator allocator)`  

```csharp
public CoverageActionData(Allocator allocator)
	{
		m_Sources = new UnsafeQueue<PathTarget>(allocator);
		m_Results = new UnsafeList<CoverageResult>(100, allocator);
		m_Parameters = default(CoverageParameters);
		m_State = PathfindActionState.Pending;
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_Sources.Dispose();
		m_Results.Dispose();
	}
```


