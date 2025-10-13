# Game.Rendering.AnimatedSystem+ClipIndex

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Rendering.AnimatedSystem+ClipIndex>`  

## Code

```csharp
public sealed struct ClipIndex : System.IEquatable<Game.Rendering.AnimatedSystem+ClipIndex>
{
    public Unity.Entities.Entity m_Style;
    public System.Int32 m_Index;

    public ClipIndex(Unity.Entities.Entity style, System.Int32 clipIndex);

    public System.Boolean Equals(Game.Rendering.AnimatedSystem+ClipIndex other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Style`  

```csharp
public Unity.Entities.Entity m_Style;
```

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```


## Constructors

- `public ClipIndex(Unity.Entities.Entity style, System.Int32 clipIndex)`  

```csharp
public ClipIndex(Unity.Entities.Entity style, System.Int32 clipIndex);
```


## Methods

- `public Equals(Game.Rendering.AnimatedSystem+ClipIndex other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Rendering.AnimatedSystem+ClipIndex other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


