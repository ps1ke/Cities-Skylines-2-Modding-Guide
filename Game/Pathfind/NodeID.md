# Game.Pathfind.NodeID

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Pathfind.NodeID>`  

## Code

```csharp
public sealed struct NodeID : System.IEquatable<Game.Pathfind.NodeID>
{
    public System.Int32 m_Index;

    public System.Boolean Equals(Game.Pathfind.NodeID other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```


## Methods

- `public Equals(Game.Pathfind.NodeID other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Pathfind.NodeID other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


