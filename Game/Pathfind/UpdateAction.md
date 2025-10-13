# Game.Pathfind.UpdateAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct UpdateAction : System.IDisposable
{
    public Unity.Collections.NativeArray<Game.Pathfind.UpdateActionData> m_UpdateData;

    public UpdateAction(System.Int32 size, Unity.Collections.Allocator allocator);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Pathfind.UpdateActionData> m_UpdateData`  

```csharp
public Unity.Collections.NativeArray<Game.Pathfind.UpdateActionData> m_UpdateData;
```


## Constructors

- `public UpdateAction(System.Int32 size, Unity.Collections.Allocator allocator)`  

```csharp
public UpdateAction(int size, Allocator allocator)
	{
		m_UpdateData = new NativeArray<UpdateActionData>(size, allocator);
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_UpdateData.Dispose();
	}
```


