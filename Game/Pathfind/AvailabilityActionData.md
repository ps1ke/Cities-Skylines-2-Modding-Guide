# Game.Pathfind.AvailabilityActionData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct AvailabilityActionData : System.IDisposable
{
    public Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Sources;
    public Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> m_Providers;
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.AvailabilityResult> m_Results;
    public Game.Pathfind.AvailabilityParameters m_Parameters;
    public Game.Pathfind.PathfindActionState m_State;

    public AvailabilityActionData(Unity.Collections.Allocator allocator, Game.Pathfind.AvailabilityParameters parameters);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Sources`  

```csharp
public Unity.Collections.UnsafeQueue<Game.Pathfind.PathTarget> m_Sources;
```

- `public Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> m_Providers`  

```csharp
public Unity.Collections.UnsafeQueue<Game.Pathfind.AvailabilityProvider> m_Providers;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.AvailabilityResult> m_Results`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.AvailabilityResult> m_Results;
```

- `public Game.Pathfind.AvailabilityParameters m_Parameters`  

```csharp
public Game.Pathfind.AvailabilityParameters m_Parameters;
```

- `public Game.Pathfind.PathfindActionState m_State`  

```csharp
public Game.Pathfind.PathfindActionState m_State;
```


## Constructors

- `public AvailabilityActionData(Unity.Collections.Allocator allocator, Game.Pathfind.AvailabilityParameters parameters)`  

```csharp
public AvailabilityActionData(Allocator allocator, AvailabilityParameters parameters)
	{
		m_Sources = new UnsafeQueue<PathTarget>(allocator);
		m_Providers = new UnsafeQueue<AvailabilityProvider>(allocator);
		m_Results = new UnsafeList<AvailabilityResult>(100, allocator);
		m_Parameters = parameters;
		m_State = PathfindActionState.Pending;
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_Sources.Dispose();
		m_Providers.Dispose();
		m_Results.Dispose();
	}
```


