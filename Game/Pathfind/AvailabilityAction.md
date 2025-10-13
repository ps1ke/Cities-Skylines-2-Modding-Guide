# Game.Pathfind.AvailabilityAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct AvailabilityAction : System.IDisposable
{
    public Unity.Collections.NativeReference<Game.Pathfind.AvailabilityActionData> m_Data;

    public Game.Pathfind.AvailabilityActionData& data { get; }

    public AvailabilityAction(Unity.Collections.Allocator allocator, Game.Pathfind.AvailabilityParameters parameters);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeReference<Game.Pathfind.AvailabilityActionData> m_Data`  

```csharp
public Unity.Collections.NativeReference<Game.Pathfind.AvailabilityActionData> m_Data;
```


## Properties

- `public Game.Pathfind.AvailabilityActionData& data { get }`  

```csharp
public Game.Pathfind.AvailabilityActionData& data { get; }
```


## Constructors

- `public AvailabilityAction(Unity.Collections.Allocator allocator, Game.Pathfind.AvailabilityParameters parameters)`  

```csharp
public AvailabilityAction(Allocator allocator, AvailabilityParameters parameters)
	{
		m_Data = new NativeReference<AvailabilityActionData>(new AvailabilityActionData(allocator, parameters), allocator);
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


