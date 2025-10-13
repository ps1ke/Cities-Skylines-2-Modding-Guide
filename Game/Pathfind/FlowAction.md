# Game.Pathfind.FlowAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct FlowAction : System.IDisposable
{
    public Unity.Collections.NativeQueue<Game.Pathfind.FlowActionData> m_FlowData;

    public FlowAction(Unity.Collections.Allocator allocator);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeQueue<Game.Pathfind.FlowActionData> m_FlowData`  

```csharp
public Unity.Collections.NativeQueue<Game.Pathfind.FlowActionData> m_FlowData;
```


## Constructors

- `public FlowAction(Unity.Collections.Allocator allocator)`  

```csharp
public FlowAction(Allocator allocator)
	{
		m_FlowData = new NativeQueue<FlowActionData>(allocator);
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_FlowData.Dispose();
	}
```


