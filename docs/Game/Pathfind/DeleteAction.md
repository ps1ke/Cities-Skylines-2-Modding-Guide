# Game.Pathfind.DeleteAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct DeleteAction : System.IDisposable
{
    public Unity.Collections.NativeArray<Game.Pathfind.DeleteActionData> m_DeleteData;

    public DeleteAction(System.Int32 size, Unity.Collections.Allocator allocator);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Pathfind.DeleteActionData> m_DeleteData`  

```csharp
public Unity.Collections.NativeArray<Game.Pathfind.DeleteActionData> m_DeleteData;
```


## Constructors

- `public DeleteAction(System.Int32 size, Unity.Collections.Allocator allocator)`  

```csharp
public DeleteAction(System.Int32 size, Unity.Collections.Allocator allocator);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


