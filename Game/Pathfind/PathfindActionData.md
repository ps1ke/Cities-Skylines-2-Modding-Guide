# Game.Pathfind.PathfindActionData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct PathfindActionData : System.IDisposable
{
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_StartTargets;
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_EndTargets;
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathfindResult> m_Result;
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathfindPath> m_Path;
    public Game.Pathfind.PathfindParameters m_Parameters;
    public Game.Pathfind.SetupTargetType m_OriginType;
    public Game.Pathfind.SetupTargetType m_DestinationType;
    public Game.Pathfind.PathfindActionState m_State;

    public PathfindActionData(System.Int32 startCount, System.Int32 endCount, Unity.Collections.Allocator allocator, Game.Pathfind.PathfindParameters parameters, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_StartTargets`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_StartTargets;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_EndTargets`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_EndTargets;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathfindResult> m_Result`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathfindResult> m_Result;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathfindPath> m_Path`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathfindPath> m_Path;
```

- `public Game.Pathfind.PathfindParameters m_Parameters`  

```csharp
public Game.Pathfind.PathfindParameters m_Parameters;
```

- `public Game.Pathfind.SetupTargetType m_OriginType`  

```csharp
public Game.Pathfind.SetupTargetType m_OriginType;
```

- `public Game.Pathfind.SetupTargetType m_DestinationType`  

```csharp
public Game.Pathfind.SetupTargetType m_DestinationType;
```

- `public Game.Pathfind.PathfindActionState m_State`  

```csharp
public Game.Pathfind.PathfindActionState m_State;
```


## Constructors

- `public PathfindActionData(System.Int32 startCount, System.Int32 endCount, Unity.Collections.Allocator allocator, Game.Pathfind.PathfindParameters parameters, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType)`  

```csharp
public PathfindActionData(int startCount, int endCount, Allocator allocator, PathfindParameters parameters, SetupTargetType originType, SetupTargetType destinationType)
	{
		if (startCount != 0)
		{
			m_StartTargets = new UnsafeList<PathTarget>(startCount, allocator);
			m_StartTargets.Length = startCount;
		}
		else
		{
			m_StartTargets = default(UnsafeList<PathTarget>);
		}
		if (endCount != 0)
		{
			m_EndTargets = new UnsafeList<PathTarget>(endCount, allocator);
			m_EndTargets.Length = endCount;
		}
		else
		{
			m_EndTargets = default(UnsafeList<PathTarget>);
		}
		m_Result = new UnsafeList<PathfindResult>(1, allocator);
		if ((parameters.m_PathfindFlags & PathfindFlags.IgnorePath) == 0)
		{
			m_Path = new UnsafeList<PathfindPath>(100, allocator);
		}
		else
		{
			m_Path = default(UnsafeList<PathfindPath>);
		}
		m_Parameters = parameters;
		m_OriginType = originType;
		m_DestinationType = destinationType;
		m_State = PathfindActionState.Pending;
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		if (m_StartTargets.IsCreated)
		{
			m_StartTargets.Dispose();
		}
		if (m_EndTargets.IsCreated)
		{
			m_EndTargets.Dispose();
		}
		m_Result.Dispose();
		if (m_Path.IsCreated)
		{
			m_Path.Dispose();
		}
	}
```


