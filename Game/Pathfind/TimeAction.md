# Game.Pathfind.TimeAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct TimeAction : System.IDisposable
{
    public Unity.Collections.NativeQueue<Game.Pathfind.TimeActionData> m_TimeData;

    public TimeAction(Unity.Collections.Allocator allocator);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeQueue<Game.Pathfind.TimeActionData> m_TimeData`  

```csharp
public Unity.Collections.NativeQueue<Game.Pathfind.TimeActionData> m_TimeData;
```


## Constructors

- `public TimeAction(Unity.Collections.Allocator allocator)`  

```csharp
public TimeAction(Allocator allocator)
	{
		m_TimeData = new NativeQueue<TimeActionData>(allocator);
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_TimeData.Dispose();
	}
```


