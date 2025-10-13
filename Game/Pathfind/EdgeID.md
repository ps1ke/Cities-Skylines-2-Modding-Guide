# Game.Pathfind.EdgeID

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Pathfind.EdgeID>`  

## Code

```csharp
public sealed struct EdgeID : System.IEquatable<Game.Pathfind.EdgeID>
{
    public System.Int32 m_Index;

    public System.Boolean Equals(Game.Pathfind.EdgeID other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```


## Methods

- `public Equals(Game.Pathfind.EdgeID other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Pathfind.EdgeID other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


