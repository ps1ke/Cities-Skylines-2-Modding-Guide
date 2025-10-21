# Game.Pathfind.CoverageAction

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct CoverageAction : System.IDisposable
{
    public Unity.Collections.NativeReference<Game.Pathfind.CoverageActionData> m_Data;

    public Game.Pathfind.CoverageActionData& data { get; }

    public CoverageAction(Unity.Collections.Allocator allocator);

    public System.Void Dispose();
}
```


## Fields

- `public Unity.Collections.NativeReference<Game.Pathfind.CoverageActionData> m_Data`  

```csharp
public Unity.Collections.NativeReference<Game.Pathfind.CoverageActionData> m_Data;
```


## Properties

- `public Game.Pathfind.CoverageActionData& data { get }`  

```csharp
public Game.Pathfind.CoverageActionData& data { get; }
```


## Constructors

- `public CoverageAction(Unity.Collections.Allocator allocator)`  

```csharp
public CoverageAction(Unity.Collections.Allocator allocator);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


