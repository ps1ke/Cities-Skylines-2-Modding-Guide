# Game.Pathfind.DensityAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct DensityAction : System.IDisposable
{
    public Unity.Collections.NativeQueue<Game.Pathfind.DensityActionData> m_DensityData;

    public DensityAction(Unity.Collections.Allocator allocator);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeQueue<Game.Pathfind.DensityActionData> m_DensityData`  

```csharp
public Unity.Collections.NativeQueue<Game.Pathfind.DensityActionData> m_DensityData;
```


## Constructors

- `public DensityAction(Unity.Collections.Allocator allocator)`  

```csharp
public DensityAction(Unity.Collections.Allocator allocator);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


