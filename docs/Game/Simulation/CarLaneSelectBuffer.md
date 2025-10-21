# Game.Simulation.CarLaneSelectBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CarLaneSelectBuffer
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
public System.Void Dispose();
```

- `public Ensure() : Unity.Collections.NativeArray<System.Single>`  

```csharp
public Unity.Collections.NativeArray<System.Single> Ensure();
```


