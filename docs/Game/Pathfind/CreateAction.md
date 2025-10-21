# Game.Pathfind.CreateAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct CreateAction : System.IDisposable
{
    public Unity.Collections.NativeArray<Game.Pathfind.CreateActionData> m_CreateData;

    public CreateAction(System.Int32 size, Unity.Collections.Allocator allocator);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Pathfind.CreateActionData> m_CreateData`  

```csharp
public Unity.Collections.NativeArray<Game.Pathfind.CreateActionData> m_CreateData;
```


## Constructors

- `public CreateAction(System.Int32 size, Unity.Collections.Allocator allocator)`  

```csharp
public CreateAction(System.Int32 size, Unity.Collections.Allocator allocator);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


