# Game.Pathfind.PathfindAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct PathfindAction : System.IDisposable
{
    public Unity.Collections.NativeReference<Game.Pathfind.PathfindActionData> m_Data;

    public Game.Pathfind.PathfindActionData& data { get; }
    public Game.Pathfind.PathfindActionData readOnlyData { get; }

    public PathfindAction(System.Int32 startCount, System.Int32 endCount, Unity.Collections.Allocator allocator, Game.Pathfind.PathfindParameters parameters, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeReference<Game.Pathfind.PathfindActionData> m_Data`  

```csharp
public Unity.Collections.NativeReference<Game.Pathfind.PathfindActionData> m_Data;
```


## Properties

- `public Game.Pathfind.PathfindActionData& data { get }`  

```csharp
public Game.Pathfind.PathfindActionData& data { get; }
```

- `public Game.Pathfind.PathfindActionData readOnlyData { get }`  

```csharp
public Game.Pathfind.PathfindActionData readOnlyData { get; }
```


## Constructors

- `public PathfindAction(System.Int32 startCount, System.Int32 endCount, Unity.Collections.Allocator allocator, Game.Pathfind.PathfindParameters parameters, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType)`  

```csharp
public PathfindAction(int startCount, int endCount, Allocator allocator, PathfindParameters parameters, SetupTargetType originType, SetupTargetType destinationType)
	{
		m_Data = new NativeReference<PathfindActionData>(new PathfindActionData(startCount, endCount, allocator, parameters, originType, destinationType), allocator);
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		data.Dispose();
		m_Data.Dispose();
	}
```


