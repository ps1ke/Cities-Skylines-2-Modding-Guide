# Game.Simulation.WatercraftLaneSelectBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct WatercraftLaneSelectBuffer
{
    private Unity.Collections.NativeArray<System.Single> m_Buffer;

    public System.Void Dispose();
    public Unity.Collections.NativeArray<System.Single> Ensure();
}
```


## Fields

- `private Unity.Collections.NativeArray<System.Single> m_Buffer`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Buffer;
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
	}
```

- `public Ensure() : Unity.Collections.NativeArray<System.Single>`  

```csharp
public NativeArray<float> Ensure()
	{
		if (!m_Buffer.IsCreated)
		{
			m_Buffer = new NativeArray<float>(64, Allocator.Temp, NativeArrayOptions.UninitializedMemory);
		}
		return m_Buffer;
	}
```


